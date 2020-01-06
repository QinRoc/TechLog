---
layout: draft
title: VisualCode中开发Go
date: 2019-03-28
updated: 2019-03-29
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

这些插件无法安装，甚至你FQ之后发现也还是无法安装

[Visual Studio Code配置GoLang开发环境](https://www.cnblogs.com/Leo_wl/p/8242465.html)

[成功安装vscode中go的相关插件](http://www.cnblogs.com/Leo_wl/p/8242628.html)

cd %GOPATH%\src\github.com\golang

如果src目录下面没有github.com\golang请自行创建

git clone https://github.com/golang/tools.git tools

需要把tools目录下的所有文件拷贝到%GOPATH%\src\golang.org\x\tools下，如果没有自行创建

插件中有几个其实不用FQ或其他方法就可以安装成功：
github.com/nsf/gocode
github.com/uudashr/gopkgs/cmd/gopkgs
github.com/fatih/gomodifytags
github.com/haya14busa/goplay/cmd/goplay
github.com/derekparker/delve/cmd/dlv

切换到GOPATH目录下，执行相关的go install 命令
go install github.com/ramya-rao-a/go-outline

go install github.com/acroca/go-symbols

go install golang.org/x/tools/cmd/guru

go install golang.org/x/tools/cmd/gorename

go install github.com/josharian/impl

go install github.com/rogpeppe/godef

go install github.com/sqs/goreturns

go install github.com/golang/lint/golint

go install github.com/cweill/gotests/gotests

# Visual Studio Code

go get -u -v github.com/nsf/gocode

go get -u -v github.com/rogpeppe/godef

go get -u -v github.com/lukehoban/go-find-references
```
github.com/lukehoban/go-find-references (download)
github.com/lukehoban/ident (download)
github.com/rogpeppe/godef (download)
```

go get -u -v github.com/lukehoban/go-outline



报错

- go get -u -v github.com/golang/lint/golint

```
github.com/golang/lint (download)
Fetching https://golang.org/x/lint?go-get=1
https fetch failed: Get https://golang.org/x/lint?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
package golang.org/x/lint: unrecognized import path "golang.org/x/lint" (https fetch: Get https://golang.org/x/lint?go-get=1: dial tcp 216.239.37.1:443: connectex: A
connection attempt failed because the connected party did not properly respond after a period of time,
```

```
github.com/golang/lint (download)
Fetching https://golang.org/x/lint?go-get=1
Parsing meta tags from https://golang.org/x/lint?go-get=1 (status code 200)
get "golang.org/x/lint": found meta tag get.metaImport{Prefix:"golang.org/x/lint", VCS:"git", RepoRoot:"https://go.googlesource.com/lint"} at https://golang.org/x/lint?go-get=1
golang.org/x/lint (download)
Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools?go-get=1
Parsing meta tags from https://golang.org/x/tools?go-get=1 (status code 200)
golang.org/x/tools (download)
Fetching https://golang.org/x/tools/go/gcexportdata?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/gcexportdata?go-get=1 (status code 200)
get "golang.org/x/tools/go/gcexportdata": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/gcexportdata?go-get=1
get "golang.org/x/tools/go/gcexportdata": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/internal/gcimporter?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/internal/gcimporter?go-get=1 (status code 200)
get "golang.org/x/tools/go/internal/gcimporter": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/gcimporter?go-get=1
get "golang.org/x/tools/go/internal/gcimporter": verifying non-authoritative meta tag
github.com/golang/lint/golint

```

https://github.com/golang/lint


- go get -u -v sourcegraph.com/sqs/goreturns

异常
```
Fetching https://sourcegraph.com/sqs/goreturns?go-get=1
Parsing meta tags from https://sourcegraph.com/sqs/goreturns?go-get=1 (status code
200)
get "sourcegraph.com/sqs/goreturns": found meta tag get.metaImport{Prefix:"sourcegraph.com/sqs/goreturns", VCS:"git", RepoRoot:"https://github.com/sqs/goreturns"} at
https://sourcegraph.com/sqs/goreturns?go-get=1
sourcegraph.com/sqs/goreturns (download)
github.com/sqs/goreturns (download)
Fetching https://golang.org/x/tools/imports?go-get=1
https fetch failed: Get https://golang.org/x/tools/imports?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
golang.org/x/tools (download)
Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
https fetch failed: Get https://golang.org/x/tools/go/ast/astutil?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/go/packages?go-get=1
https fetch failed: Get https://golang.org/x/tools/go/packages?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed
because connected host has failed to respond.
Fetching https://golang.org/x/tools/go/gcexportdata?go-get=1
https fetch failed: Get https://golang.org/x/tools/go/gcexportdata?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/go/internal/gcimporter?go-get=1
https fetch failed: Get https://golang.org/x/tools/go/internal/gcimporter?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/go/internal/packagesdriver?go-get=1
https fetch failed: Get https://golang.org/x/tools/go/internal/packagesdriver?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the
connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/internal/gopathwalk?go-get=1
https fetch failed: Get https://golang.org/x/tools/internal/gopathwalk?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/internal/fastwalk?go-get=1
https fetch failed: Get https://golang.org/x/tools/internal/fastwalk?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/internal/semver?go-get=1
https fetch failed: Get https://golang.org/x/tools/internal/semver?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
Fetching https://golang.org/x/tools/internal/module?go-get=1
https fetch failed: Get https://golang.org/x/tools/internal/module?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
sourcegraph.com/sqs/goreturns
```

正常
```
Fetching https://sourcegraph.com/sqs/goreturns?go-get=1
Parsing meta tags from https://sourcegraph.com/sqs/goreturns?go-get=1 (status code 200)
get "sourcegraph.com/sqs/goreturns": found meta tag get.metaImport{Prefix:"sourcegraph.com/sqs/goreturns", VCS:"git", RepoRoot:"https://github.com/sqs/goreturns"} at https://sourcegraph.com/sqs/goreturns?go-get=1
sourcegraph.com/sqs/goreturns (download)
github.com/sqs/goreturns (download)
Fetching https://golang.org/x/tools/imports?go-get=1
Parsing meta tags from https://golang.org/x/tools/imports?go-get=1 (status code 200)
get "golang.org/x/tools/imports": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/imports?go-get=1
get "golang.org/x/tools/imports": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools?go-get=1
Parsing meta tags from https://golang.org/x/tools?go-get=1 (status code 200)
golang.org/x/tools (download)
Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/packages?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/packages?go-get=1 (status code 200)
get "golang.org/x/tools/go/packages": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/packages?go-get=1
get "golang.org/x/tools/go/packages": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/gcexportdata?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/gcexportdata?go-get=1 (status code 200)
get "golang.org/x/tools/go/gcexportdata": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/gcexportdata?go-get=1
get "golang.org/x/tools/go/gcexportdata": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/internal/gcimporter?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/internal/gcimporter?go-get=1 (status code 200)
get "golang.org/x/tools/go/internal/gcimporter": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/gcimporter?go-get=1
get "golang.org/x/tools/go/internal/gcimporter": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/internal/packagesdriver?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/internal/packagesdriver?go-get=1 (status code 200)
get "golang.org/x/tools/go/internal/packagesdriver": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/packagesdriver?go-get=1
get "golang.org/x/tools/go/internal/packagesdriver": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/internal/gopathwalk?go-get=1
Parsing meta tags from https://golang.org/x/tools/internal/gopathwalk?go-get=1 (status code 200)
get "golang.org/x/tools/internal/gopathwalk": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/gopathwalk?go-get=1
get "golang.org/x/tools/internal/gopathwalk": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/internal/fastwalk?go-get=1
Parsing meta tags from https://golang.org/x/tools/internal/fastwalk?go-get=1 (status code 200)
get "golang.org/x/tools/internal/fastwalk": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/fastwalk?go-get=1
get "golang.org/x/tools/internal/fastwalk": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/internal/semver?go-get=1
Parsing meta tags from https://golang.org/x/tools/internal/semver?go-get=1 (status code 200)
get "golang.org/x/tools/internal/semver": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/semver?go-get=1
get "golang.org/x/tools/internal/semver": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/internal/module?go-get=1
Parsing meta tags from https://golang.org/x/tools/internal/module?go-get=1 (status code 200)
get "golang.org/x/tools/internal/module": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/module?go-get=1
get "golang.org/x/tools/internal/module": verifying non-authoritative meta tag
golang.org/x/tools/internal/semver
golang.org/x/tools/internal/fastwalk
golang.org/x/tools/internal/module
golang.org/x/tools/go/internal/packagesdriver
golang.org/x/tools/internal/gopathwalk
golang.org/x/tools/go/packages
golang.org/x/tools/imports
sourcegraph.com/sqs/goreturns

```

- go get -u -v golang.org/x/tools/cmd/gorename

正常：
```
Fetching https://golang.org/x/tools/cmd/gorename?go-get=1
Parsing meta tags from https://golang.org/x/tools/cmd/gorename?go-get=1 (status code 200)
get "golang.org/x/tools/cmd/gorename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/cmd/gorename?go-get=1
get "golang.org/x/tools/cmd/gorename": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools?go-get=1
Parsing meta tags from https://golang.org/x/tools?go-get=1 (status code 200)
golang.org/x/tools (download)
Fetching https://golang.org/x/tools/go/buildutil?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/buildutil?go-get=1 (status code 200)
get "golang.org/x/tools/go/buildutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/buildutil?go-get=1
get "golang.org/x/tools/go/buildutil": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/refactor/rename?go-get=1
Parsing meta tags from https://golang.org/x/tools/refactor/rename?go-get=1 (status code 200)
get "golang.org/x/tools/refactor/rename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/rename?go-get=1
get "golang.org/x/tools/refactor/rename": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/loader?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/loader?go-get=1 (status code 200)
get "golang.org/x/tools/go/loader": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/loader?go-get=1
get "golang.org/x/tools/go/loader": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/internal/cgo?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/internal/cgo?go-get=1 (status code 200)
get "golang.org/x/tools/go/internal/cgo": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/cgo?go-get=1
get "golang.org/x/tools/go/internal/cgo": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/go/types/typeutil?go-get=1
Parsing meta tags from https://golang.org/x/tools/go/types/typeutil?go-get=1 (status code 200)
get "golang.org/x/tools/go/types/typeutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/types/typeutil?go-get=1
get "golang.org/x/tools/go/types/typeutil": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/refactor/importgraph?go-get=1
Parsing meta tags from https://golang.org/x/tools/refactor/importgraph?go-get=1 (status code 200)
get "golang.org/x/tools/refactor/importgraph": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/importgraph?go-get=1
get "golang.org/x/tools/refactor/importgraph": verifying non-authoritative meta tag
Fetching https://golang.org/x/tools/refactor/satisfy?go-get=1
Parsing meta tags from https://golang.org/x/tools/refactor/satisfy?go-get=1 (status code 200)
get "golang.org/x/tools/refactor/satisfy": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/satisfy?go-get=1
get "golang.org/x/tools/refactor/satisfy": verifying non-authoritative meta tag
golang.org/x/tools/go/internal/cgo
golang.org/x/tools/go/buildutil
golang.org/x/tools/go/types/typeutil
golang.org/x/tools/refactor/importgraph
golang.org/x/tools/go/loader
golang.org/x/tools/refactor/satisfy
golang.org/x/tools/refactor/rename
golang.org/x/tools/cmd/gorename

```

---

#

The Go extension is better with the latest version of "go-outline". Use "go get -u -v github.com/ramya-rao-a/go-outline" to update

Installing github.com/ramya-rao-a/go-outline SUCCEEDED

All tools successfully installed. You're ready to Go :).

---

#
```
C:\Users\Roc\AppData\Local\Temp\vscode-gokR0jiB\go-code-check .
go: golang.org/x/net@v0.0.0-20181011144130-49bb7cea24b1: unrecognized import path "golang.org/x/net" (https fetch: Get https://golang.org/x/net?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)
go: google.golang.org/grpc@v1.16.0: unrecognized import path "google.golang.org/grpc" (https fetch: Get https://google.golang.org/grpc?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)
go: error loading module requirements
```

# go 设置代理

让go get用上http代理:
windows: go get前设置代理： 执行 set http_proxy=http://localhost:8118/ set https_proxy=http://localhost:8118,然后go get就会走代理了

让git clone用上socket5/http代理:
修改 $USER/.gitconfig
添加配置项如下：当git clone的时候就会走代理了，当不需要代理的时候可以注释掉

 [https]
     proxy = http://localhost:8118 #注意没有引号

 [http]
     proxy = http://localhost:8118



visual studio code:

.vscode\launch.json: "env": { "https_proxy" : "http://127.0.0.1:1080&#34; },


[如何在长城后面go get一些库](https://colobu.com/2017/01/26/how-to-go-get-behind-GFW/)
shadowsocks 的安装和使用我就不说了，请自行搜索。Shadowsocks 虽然能访问一些屏蔽的站点比如golang.org,但是它基于socks5协议，对于go get来说，依然不可用。


在本机启动一个http代理，以shadowsocks为二级代理。

如果没有代理，而你又需要golang.org/x／...的包，你可以手工在你的GOPATH下创建这些目录，然后 git clone github.com/golang/xxx相应的目录即可(xxx替换成泥需要的库，比如net)。

$ go get -u golang.org/x/lint/golint
package golang.org/x/tools/go/ast/astutil: golang.org/x/tools is a custom import path for https://go.googlesource.com/tools, but C:\Program\Go\src\golang.org\x\tools is checked out from https://github.com/golang/tools.git
package golang.org/x/tools/go/gcexportdata: golang.org/x/tools is a custom import path for https://go.googlesource.com/tools, but C:\Program\Go\src\golang.org\x\tools is checked out from https://github.com/golang/tools.git

删除 .git

package golang.org/x/tools/go/ast/astutil: directory "C:\\Program\\Go\\src\\golang.org\\x\\tools\\go\\ast\\astutil" is not using a known version control system
package golang.org/x/tools/go/gcexportdata: directory "C:\\Program\\Go\\src\\golang.org\\x\\tools\\go\\gcexportdata" is not using a known version control system

删除tools文件夹


>export http_proxy 与 set http_proxy
[Win/Linux 命令行、终端和 Git 代理设置
](https://g2ex.github.io/2017/10/22/windows-linux-git-proxy-cmd/)
Windows 命令行代理设置
HTTP 代理设置：

set http_proxy=http://127.0.0.1:8118
set https_proxy=http://127.0.0.1:8118
SOCKS5 代理设置：

set http_proxy=socks5://127.0.0.1:1080
set https_proxy=socks5://127.0.0.1:1080
可以通过 echo %http_proxy% 命令查看是否设置成功。

取消代理设置：

set http_proxy=
set https_proxy=

Linux 终端代理设置
临时代理设置
Linux 终端设置 HTTP 代理（只对当前终端有效）：

$ export http_proxy=http://127.0.0.1:8118
$ export https_proxy=http://127.0.0.1:8118
Linux 中设置 SOCKS5 代理（只对当前终端有效）：

$ export http_proxy=socks5://127.0.0.1:1080
$ export https_proxy=socks5://127.0.0.1:1080
设置终端中的 wget、curl 等都走 SOCKS5 代理（只对当前终端有效）：

$ export ALL_PROXY=socks5://127.0.0.1:1080
Linux 终端中取消代理设置：

$ unset http_proxy
$ unset https_proxy
$ unset ALL_RPOXY
永久代理设置
将代理命令写入配置文件 ~/.profile 或 ~/.bashrc 或 ~/.zshrc 中：

HTTP 代理设置
export http_proxy=http://127.0.0.1:8118
export https_proxy=http://127.0.0.1:8118
或

SOCKS5 代理设置
export http_proxy=socks5://127.0.0.1:1080
export https_proxy=socks5://127.0.0.1:1080
或

强制终端中的 wget、curl 等都走 SOCKS5 代理
export ALL_PROXY=socks5://127.0.0.1:1080

Git 设置代理
代理格式 [protocol://][user[:password]@]proxyhost[:port]
参考 https://git-scm.com/docs/git-config

设置 HTTP 代理：

git config --global http.proxy http://127.0.0.1:8118
git config --global https.proxy http://127.0.0.1:8118
设置 SOCKS5 代理：

git config --global http.proxy socks5://127.0.0.1:1080
git config --global https.proxy socks5://127.0.0.1:1080
Git 取消代理设置：

git config --global --unset http.proxy
git config --global --unset https.proxy



$ go get -u -v golang.org/x/net
Fetching https://golang.org/x/net?go-get=1
Parsing meta tags from https://golang.org/x/net?go-get=1 (status code 200)
get "golang.org/x/net": found meta tag get.metaImport{Prefix:"golang.org/x/net", VCS:"git", RepoRoot:"https://go.googlesource.com/net"} at https://golang.org/x/net?go-get=1
golang.org/x/net (download)
package golang.org/x/net: no Go files in C:\Users\Roc\go\src\golang.org\x\net
