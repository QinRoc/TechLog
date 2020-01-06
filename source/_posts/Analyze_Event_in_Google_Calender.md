---
layout: post
title: 谷歌日历数据解析
date: 2020-01-05
updated:
thumbnail:
comments: true
tags: [Google,Calender]
categories:
permalink: true
toc: true
---

## 1. 缘起

做2019年终工作总结PPT的时候想放入一些统计图，其中包括了本年度参与的会议种类及数目。由于平时使用Google Calender安排日程，所以想是否能从其中进行分析。

## 2. 过程

### ~~2.1 搜索~~

第一个想法是搜索相关关键字，但是发现只能搜出来近期的相应内容。

### 2.2 导出数据

看Google Calender的设置的时候发现能够导出数据。于是进行导出。

导出是一个zip压缩的文件，直接打开的话，会在Win10的邮件应用中执行导入操作（需要确认）。

用文本编辑器打开这个文件，发现都是文本，而且是把使用以来的全部数据都导出来了。

### 2.3 分析数据

分析记录，尝试找出数据规律。发现近期的记录基本都是这样的重复：

```txt
BEGIN:VEVENT
DTSTART:20181126T013000Z
DTEND:20181126T023000Z
DTSTAMP:20200105T011844Z
UID:0rm22n1nkgdibuhfao2mij324p@google.com
CREATED:20181122T064618Z
DESCRIPTION:
LAST-MODIFIED:20181122T064658Z
LOCATION:xx室
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:xxx需求评审
TRANSP:OPAQUE
END:VEVENT
```

更早的记录的日历事件的字段会有差别，但是我只需要2019年的，所以也不关心。

经过观察，我只需要提取出这三个字段的内容即可：

```txt
DTSTART 事件开始时间
LOCATION 事件地点
SUMMARY 事件标题
```

### 3. 提取记录

使用Python提取数据，用到的代码如下：

```Python
import re

#正则模式
#单个事件记录
event_pattern=re.compile(r'^BEGIN:VEVEN.*?END:VEVENT$',re.MULTILINE|re.DOTALL)
#2019年的起始时间
start_2019_pattern=re.compile(r'^DTSTART:2019.*?$',re.MULTILINE)
#提取起始时间
start_pattern=re.compile(r'^DTSTART:(?P<start>.+?)$',re.MULTILINE)
#提取标题
summary_pattern=re.compile(r'^SUMMARY:(?P<summary>.+?)$',re.MULTILINE)
#提取地点
location_pattern=re.compile(r'^LOCATION:(?P<location>.+?)$',re.MULTILINE)

#屏蔽的关键词，运行多次，逐步完善
block_summary = ["做饭","健身","钢琴",'理财','制定周计划','聚餐','洗牙','电影','航班','生日','取消','跑步','火车','加班','理发','中医理疗','收拾行李']

def deal_event(i,file):
    #提取起始时间为2019年的记录
    start2019Result = start_2019_pattern.findall(i)
    if len(start2019Result):
        #该事件属于2019年
        #提取开始时间
        startResult = start_pattern.search(i).group('start')
        #提取标题
        summaryResult = summary_pattern.search(i).group('summary')
        #提取地点
        locationSearchResult = location_pattern.search(i)
        locationResult = ''
        if locationSearchResult:
            #提出出了地点
            locationResult = locationSearchResult.group('location')

        #标记是否需要屏蔽这个事件（与工作无关）
        is_block = 0
        for block in block_summary:
            if block in summaryResult:
                is_block = 1
        if not is_block:
            #不屏蔽、想要的事件
            #写入结果文件
            file.write(startResult+','+locationResult+','+summaryResult)
            file.write('\n')

#导出的日历数据文件，保存成了txt格式文件
calenderFile = open('./20200105-GoogleCalender.txt')
#文件数据
calenderString = calenderFile.read()
#提取事件列表
extractEventList = event_pattern.findall(calenderString)
#保存的文件
filterEvent = open('./filterEvent.txt','w')
for event in  extractEventList:
    deal_event(event,filterEvent)
```

其中的难点在于多行正则提取。

提取的结果格式如下：

```txt
20190716T080000Z,xx会议室,xxx会议
20190716T080000Z,,xxx会议
```

由于安排日程的时候比较随意，命名不规范，所以无法做到完整的分类统计，这次只能先人工分类统计。

### 后续计划

1. 制定日程名称规范，便于之后的统计。
2. 完善代码。
