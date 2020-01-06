---
layout: post
title: 日语分词
date: 2020-01-04
updated:
thumbnail:
comments: true
tags: [Japanese,Segmentation]
categories:
permalink: true
toc: true
---


## 分词库

Google和Github上以“japanese segmentation”为关键词搜索：

- [gse](https://github.com/go-ego/gse) #Go

> Go efficient text segmentation @vcaesar; support english, chinese, japanese and other. Go 语言高性能分词

- [kagome](https://github.com/ikawaha/kagome) #Go

> Self-contained Japanese Morphological Analyzer written in pure Go

- [Sudachi](https://github.com/WorksApplications/Sudachi) #Java #Python

> A Japanese Tokenizer for Business

- [SudachiPy](https://github.com/WorksApplications/SudachiPy)

> Python version of Sudachi, a Japanese tokenizer.

- [SudachiDict](https://github.com/WorksApplications/SudachiDict)

> A lexicon for Sudachi

- [nagisa](https://github.com/taishi-i/nagisa) #Python

> A Japanese tokenizer based on recurrent neural networks

- [Kuromoji](https://www.atilika.org/)
> Kuromoji is an open source Japanese morphological analyzer written in Java.

## 环境准备

选用SudachiPy进行分词。

## 安装SudachiPy库

```shell
python3 -m pip install SudachiPy

```

出现的问题:
>x86_64-linux-gnu-gcc: error trying to exec 'cc1plus': execvp: No such file or directory

[g++: error trying to exec 'cc1plus': execvp: No such file or directory](https://stackoverflow.com/questions/22414109/g-error-trying-to-exec-cc1plus-execvp-no-such-file-or-directory/27944551#27944551)

```shell
sudo apt-get install g++
python3 -m pip install https://object-storage.tyo2.conoha.io/v1/nc_2520839e1f9641b08211a5c85243124a/sudachi/SudachiDict_core-20191224.tar.gz
```

## 安装词典

```shell
python3 -m pip install https://object-storage.tyo2.conoha.io/v1/nc_2520839e1f9641b08211a5c85243124a/sudachi/SudachiDict_core-20191224.tar.gz
```

出现的问题：网络不佳，自行下载后安装

```shell
python3 -m pip install ./SudachiDict_core-20191224.tar.gz.tar
```

## 编码实现

SudachiPy的使用按照[官方示例](https://github.com/WorksApplications/SudachiPy)即可。
我使用的是SplitMode.B。

```Python
from sudachipy import tokenizer
from sudachipy import dictionary

tokenizer_obj = dictionary.Dictionary().create()
mode = tokenizer.Tokenizer.SplitMode.B
list = [m.surface() for m in tokenizer_obj.tokenize("国家公務員", mode)]
print(list)
# => ['国家', '公務員']
```
