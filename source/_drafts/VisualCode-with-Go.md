---
layout: draft
title: VisualCode中开发Go
date: 2019-03-28
updated: 
thumbnail: 
comments: true
tags: [Go,VisualCode] 
categories: 
permalink: true
toc: true
---

> go语言设置代理

```
{
	"resource": "/c:/Code/GitHub/QinRoc/goim/benchmarks/multi_push/main.go",
	"owner": "go",
	"severity": 8,
	"message": "go: golang.org/x/net@v0.0.0-20181011144130-49bb7cea24b1: unrecognized import path \"golang.org/x/net\" (https fetch: Get https://golang.org/x/net?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)\ngo: google.golang.org/grpc@v1.16.0: unrecognized import path \"google.golang.org/grpc\" (https fetch: Get https://google.golang.org/grpc?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)\ngo: error loading module requirements\n",
	"source": "go",
	"startLineNumber": 1,
	"startColumn": 1,
	"endLineNumber": 1,
	"endColumn": 13
}
```

```
C:\Code\GitHub\QinRoc\goim\benchmarks\multi_push>Finished running tool: C:\Program\Go\bin\go.exe build -o C:\Users\Roc\AppData\Local\Temp\vscode-goDoJ1ON\go-code-check .
go: golang.org/x/net@v0.0.0-20181011144130-49bb7cea24b1: unrecognized import path "golang.org/x/net" (https fetch: Get https://golang.org/x/net?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)
go: google.golang.org/grpc@v1.16.0: unrecognized import path "google.golang.org/grpc" (https fetch: Get https://google.golang.org/grpc?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)
go: error loading module requirements
```