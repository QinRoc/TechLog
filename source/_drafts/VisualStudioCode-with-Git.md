---
layout: draft
title: VisualCode中Git使用
date: 2019-03-29
updated:
thumbnail:
comments: true
tags: [Git,VisualCode]
categories:
permalink: true
toc: true
---

>VisualCode中Git多账号

>Network Block

```
Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch
fatal: unable to access 'https://github.com/QinRoc/TechLog.git/': OpenSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch git@dev
fatal: 'git@dev' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git remote -v
origin  https://github.com/QinRoc/TechLog.git (fetch)
origin  https://github.com/QinRoc/TechLog.git (push)

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch
fatal: unable to access 'https://github.com/QinRoc/TechLog.git/': OpenSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config --global http.proxy
http://127.0.0.1:1080

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config --global --unset http.proxy

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ ls
_config.yml  node_modules/  package-lock.json  scaffolds/  themes/
db.json      package.json   README.md          source/

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ ls source/post
ls: cannot access 'source/post': No such file or directory

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ ls source/_posts/
Blog-1-0-0.md  One-Client-with-Multi-Git-Account.md  Win-Linux-Dual-Sys.md

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch
fatal: unable to access 'https://github.com/QinRoc/TechLog.git/': OpenSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch
c

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config -k
error: unknown switch `k'
usage: git config [<options>]

Config file location
    --global              use global config file
    --system              use system config file
    --local               use repository config file
    -f, --file <file>     use given config file
    --blob <blob-id>      read config from given blob object

Action
    --get                 get value: name [value-regex]
    --get-all             get all values: key [value-regex]
    --get-regexp          get values for regexp: name-regex [value-regex]
    --get-urlmatch        get value specific for the URL: section[.var] URL
    --replace-all         replace all matching variables: name value [value_regex]
    --add                 add a new variable: name value
    --unset               remove a variable: name [value-regex]
    --unset-all           remove all matches: name [value-regex]
    --rename-section      rename section: old-name new-name
    --remove-section      remove a section: name
    -l, --list            list all
    -e, --edit            open an editor
    --get-color           find the color configured: slot [default]
    --get-colorbool       find the color setting: slot [stdout-is-tty]

Type
    -t, --type <>         value is given this type
    --bool                value is "true" or "false"
    --int                 value is decimal number
    --bool-or-int         value is --bool or --int
    --path                value is a path (file or directory name)
    --expiry-date         value is an expiry date

Other
    -z, --null            terminate values with NUL byte
    --name-only           show variable names only
    --includes            respect include directives on lookup
    --show-origin         show origin of config (file, standard input, blob, command line)
    --default <value>     with --get, use default value when missing entry


Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config -l
core.symlinks=true
core.autocrlf=true
core.fscache=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
help.format=html
rebase.autosquash=true
http.sslcainfo=C:/Program/Emulator/Git/mingw64/ssl/certs/ca-bundle.crt
http.sslbackend=openssl
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
credential.helper=manager
core.editor='C:\Program\Document\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
core.symlinks=true
core.autocrlf=true
core.fscache=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
help.format=html
rebase.autosquash=true
http.sslcainfo=C:/Program/Emulator/Git/mingw64/ssl/certs/ca-bundle.crt
http.sslbackend=openssl
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
credential.helper=manager
core.editor='C:\Program\Document\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
winupdater.recentlyseenversion=2.19.1.windows.1
https.proxy=https://127.0.0.1:1080
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
remote.origin.url=https://github.com/QinRoc/TechLog.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
user.name=QinRoc
user.email=qinrocdev@gmail.com
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
core.symlinks=true
core.autocrlf=true
core.fscache=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
help.format=html
rebase.autosquash=true
http.sslcainfo=C:/Program/Emulator/Git/mingw64/ssl/certs/ca-bundle.crt
http.sslbackend=openssl
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
credential.helper=manager
core.editor='C:\Program\Document\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
winupdater.recentlyseenversion=2.19.1.windows.1
https.proxy=https://127.0.0.1:1080
core.repositoryformatversion=0
itc^C

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config unset https.proxy
error: key does not contain a section: unset

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config --unset https.proxy

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch


Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config -l | grep proxy
https.proxy=https://127.0.0.1:1080

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config --unset https.proxy

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config -l | grep proxy
https.proxy=https://127.0.0.1:1080

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config --global --unset https.proxy

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git config -l | grep proxy

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git remote -v
origin  https://github.com/QinRoc/TechLog.git (fetch)
origin  https://github.com/QinRoc/TechLog.git (push)

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git fetch origin gh-pages-hexo
From https://github.com/QinRoc/TechLog
 * branch            gh-pages-hexo -> FETCH_HEAD

Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
$ git log -p gh-pages-hexo origin/gh-pages-hexo
commit 14d4d2aded14f3c5272359f76b50eec2f02a01cc (origin/gh-pages-hexo)
Author: QinRoc <qinrocdev@gmail.com>
Date:   Fri Mar 29 18:57:02 2019 +0800

    docs: add 2 drafts

diff --git a/source/_drafts/Software-Project-Development-Specification-Publicity-Conference.md b/source/_drafts/Software-Project-Development-Specification-Publicity-Conference.md
new file mode 100644
index 0000000..1afaf20
--- /dev/null
+++ b/source/_drafts/Software-Project-Development-Specification-Publicity-Conference.md
@@ -0,0 +1,20 @@
+---
+#Drafts are not displayed by default. You can add the --draft option when running Hexo or enable the render_drafts setting in _config.yml to render drafts.
+#https://hexo.io/docs/writing
+#https://hexo.io/docs/front-matter
+layout: draft
+title: 软件项目开发规范宣贯会反思
+date: 2019-03-29
+updated:
+thumbnail:
+comments: true
+tags: Review
+categories:
+permalink: true
+toc: true
+---
+
+只关注自己的工作，没有把这个工作当做自己的项目。
+
+未考虑KX负责的部分如何做好，如何配合。
+
diff --git a/source/_drafts/VisualCode-with-Go.md b/source/_drafts/VisualCode-with-Go.md
index 0645824..18e2444 100644
--- a/source/_drafts/VisualCode-with-Go.md
+++ b/source/_drafts/VisualCode-with-Go.md
@@ -2,11 +2,11 @@
 layout: draft
 title: VisualCode中开发Go
 date: 2019-03-28
-updated:
-thumbnail:
+updated: 2019-03-29
+thumbnail:
 comments: true
-tags: [Go,VisualCode]
-categories:
+tags: [Go,VisualCode]
+categories:
 permalink: true
 toc: true
 ---
@@ -32,4 +32,394 @@ C:\Code\GitHub\QinRoc\goim\benchmarks\multi_push>Finished running tool: C:\Progr
 go: golang.org/x/net@v0.0.0-20181011144130-49bb7cea24b1: unrecognized import path "golang.org/x/net" (https fetch: Get https://golang.org/x/net?go-get=1: dialtcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.)
 go: google.golang.org/grpc@v1.16.0: unrecognized import path "google.golang.org/grpc" (https fetch: Get https://google.golang.org/grpc?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected partydid not properly respond after a period of time, or established connection failed because connected host has failed to respond.)
 go: error loading module requirements
-```
\ No newline at end of file
+```
+
+这些插件无法安装，甚至你FQ之后发现也还是无法安装
+
+[Visual Studio Code配置GoLang开发环境](https://www.cnblogs.com/Leo_wl/p/8242465.html)
+
+[成功安装vscode中go的相关插件](http://www.cnblogs.com/Leo_wl/p/8242628.html)
+
+cd %GOPATH%\src\github.com\golang
+
+如果src目录下面没有github.com\golang请自行创建
+
+git clone https://github.com/golang/tools.git tools
+
+需要把tools目录下的所有文件拷贝到%GOPATH%\src\golang.org\x\tools下，如果没有自
行创建
+
+插件中有几个其实不用FQ或其他方法就可以安装成功：
+github.com/nsf/gocode
+github.com/uudashr/gopkgs/cmd/gopkgs
+github.com/fatih/gomodifytags
+github.com/haya14busa/goplay/cmd/goplay
+github.com/derekparker/delve/cmd/dlv
+
+切换到GOPATH目录下，执行相关的go install 命令
+go install github.com/ramya-rao-a/go-outline
+
+go install github.com/acroca/go-symbols
+
+go install golang.org/x/tools/cmd/guru
+
+go install golang.org/x/tools/cmd/gorename
+
+go install github.com/josharian/impl
+
+go install github.com/rogpeppe/godef
+
+go install github.com/sqs/goreturns
+
+go install github.com/golang/lint/golint
+
+go install github.com/cweill/gotests/gotests
+
+# Visual Studio Code
+
+go get -u -v github.com/nsf/gocode
+
+go get -u -v github.com/rogpeppe/godef
+
+go get -u -v github.com/lukehoban/go-find-references
+```
+github.com/lukehoban/go-find-references (download)
+github.com/lukehoban/ident (download)
+github.com/rogpeppe/godef (download)
+```
+
+go get -u -v github.com/lukehoban/go-outline
+
+
+
+报错
+
+- go get -u -v github.com/golang/lint/golint
+
+```
+github.com/golang/lint (download)
+Fetching https://golang.org/x/lint?go-get=1
+https fetch failed: Get https://golang.org/x/lint?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+package golang.org/x/lint: unrecognized import path "golang.org/x/lint" (httpsfetch: Get https://golang.org/x/lint?go-get=1: dial tcp 216.239.37.1:443: connectex: A
+connection attempt failed because the connected party did not properly respondafter a period of time,
+```
+
+```
+github.com/golang/lint (download)
+Fetching https://golang.org/x/lint?go-get=1
+Parsing meta tags from https://golang.org/x/lint?go-get=1 (status code 200)
+get "golang.org/x/lint": found meta tag get.metaImport{Prefix:"golang.org/x/lint", VCS:"git", RepoRoot:"https://go.googlesource.com/lint"} at https://golang.org/x/lint?go-get=1
+golang.org/x/lint (download)
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
+get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools?go-get=1
+Parsing meta tags from https://golang.org/x/tools?go-get=1 (status code 200)
+golang.org/x/tools (download)
+Fetching https://golang.org/x/tools/go/gcexportdata?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/gcexportdata?go-get=1 (status code 200)
+get "golang.org/x/tools/go/gcexportdata": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/gcexportdata?go-get=1
+get "golang.org/x/tools/go/gcexportdata": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/gcimporter?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/gcimporter?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/gcimporter": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/gcimporter?go-get=1
+get "golang.org/x/tools/go/internal/gcimporter": verifying non-authoritative meta tag
+github.com/golang/lint/golint
+
+```
+
+https://github.com/golang/lint
+
+
+- go get -u -v sourcegraph.com/sqs/goreturns
+
+异常
+```
+Fetching https://sourcegraph.com/sqs/goreturns?go-get=1
+Parsing meta tags from https://sourcegraph.com/sqs/goreturns?go-get=1 (status code
+200)
+get "sourcegraph.com/sqs/goreturns": found meta tag get.metaImport{Prefix:"sourcegraph.com/sqs/goreturns", VCS:"git", RepoRoot:"https://github.com/sqs/goreturns"} at
+https://sourcegraph.com/sqs/goreturns?go-get=1
+sourcegraph.com/sqs/goreturns (download)
+github.com/sqs/goreturns (download)
+Fetching https://golang.org/x/tools/imports?go-get=1
+https fetch failed: Get https://golang.org/x/tools/imports?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+golang.org/x/tools (download)
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+https fetch failed: Get https://golang.org/x/tools/go/ast/astutil?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/go/packages?go-get=1
+https fetch failed: Get https://golang.org/x/tools/go/packages?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed
+because connected host has failed to respond.
+Fetching https://golang.org/x/tools/go/gcexportdata?go-get=1
+https fetch failed: Get https://golang.org/x/tools/go/gcexportdata?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/go/internal/gcimporter?go-get=1
+https fetch failed: Get https://golang.org/x/tools/go/internal/gcimporter?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/go/internal/packagesdriver?go-get=1
+https fetch failed: Get https://golang.org/x/tools/go/internal/packagesdriver?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the
+connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/internal/gopathwalk?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/gopathwalk?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because theconnected party did not properly respond after a period of time, or establishedconnection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/internal/fastwalk?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/fastwalk?go-get=1:dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/internal/semver?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/semver?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/internal/module?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/module?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+sourcegraph.com/sqs/goreturns
+```
+
+正常
+```
+Fetching https://sourcegraph.com/sqs/goreturns?go-get=1
+Parsing meta tags from https://sourcegraph.com/sqs/goreturns?go-get=1 (status code 200)
+Fetching https://golang.org/x/tools/internal/fastwalk?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/fastwalk?go-get=1:dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/internal/semver?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/semver?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+Fetching https://golang.org/x/tools/internal/module?go-get=1
+https fetch failed: Get https://golang.org/x/tools/internal/module?go-get=1: dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
+sourcegraph.com/sqs/goreturns
+```
+
+正常
+```
+Fetching https://sourcegraph.com/sqs/goreturns?go-get=1
+Parsing meta tags from https://sourcegraph.com/sqs/goreturns?go-get=1 (status code 200)
+get "sourcegraph.com/sqs/goreturns": found meta tag get.metaImport{Prefix:"sourcegraph.com/sqs/goreturns", VCS:"git", RepoRoot:"https://github.com/sqs/goreturns"} at https://sourcegraph.com/sqs/goreturns?go-get=1
+sourcegraph.com/sqs/goreturns (download)
+github.com/sqs/goreturns (download)
+Fetching https://golang.org/x/tools/imports?go-get=1
+Parsing meta tags from https://golang.org/x/tools/imports?go-get=1 (status code 200)
+get "golang.org/x/tools/imports": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/imports?go-get=1
+get "golang.org/x/tools/imports": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools?go-get=1
+Parsing meta tags from https://golang.org/x/tools?go-get=1 (status code 200)
+golang.org/x/tools (download)
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
+get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/packages?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/packages?go-get=1 (statuscode 200)
+get "golang.org/x/tools/go/packages": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/packages?go-get=1
+get "golang.org/x/tools/go/packages": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/gcexportdata?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/gcexportdata?go-get=1 (status code 200)
+get "golang.org/x/tools/go/gcexportdata": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/gcexportdata?go-get=1
+get "golang.org/x/tools/go/gcexportdata": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/gcimporter?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/gcimporter?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/gcimporter": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/gcimporter?go-get=1
+get "golang.org/x/tools/go/internal/gcimporter": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/packagesdriver?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/packagesdriver?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/packagesdriver": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/internal/packagesdriver?go-get=1
+get "golang.org/x/tools/go/internal/packagesdriver": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/internal/gopathwalk?go-get=1
+Parsing meta tags from https://golang.org/x/tools/internal/gopathwalk?go-get=1(status code 200)
+get "golang.org/x/tools/internal/gopathwalk": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/gopathwalk?go-get=1
+get "golang.org/x/tools/internal/gopathwalk": verifying non-authoritative metatag
+Fetching https://golang.org/x/tools/internal/fastwalk?go-get=1
+Parsing meta tags from https://golang.org/x/tools/internal/fastwalk?go-get=1 (status code 200)
+get "golang.org/x/tools/internal/fastwalk": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/fastwalk?go-get=1
+get "golang.org/x/tools/internal/fastwalk": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/internal/semver?go-get=1
+Parsing meta tags from https://golang.org/x/tools/internal/semver?go-get=1 (status code 200)
+get "golang.org/x/tools/internal/semver": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/semver?go-get=1
+get "golang.org/x/tools/internal/semver": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/internal/module?go-get=1
+Parsing meta tags from https://golang.org/x/tools/internal/module?go-get=1 (status code 200)
+get "golang.org/x/tools/internal/module": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/internal/module?go-get=1
+get "golang.org/x/tools/internal/module": verifying non-authoritative meta tag
+golang.org/x/tools/internal/semver
+golang.org/x/tools/internal/fastwalk
+golang.org/x/tools/internal/module
+golang.org/x/tools/go/internal/packagesdriver
+golang.org/x/tools/internal/gopathwalk
+golang.org/x/tools/go/packages
+golang.org/x/tools/imports
+sourcegraph.com/sqs/goreturns
+
+```
+
+- go get -u -v golang.org/x/tools/cmd/gorename
+
+正常：
+```
+Fetching https://golang.org/x/tools/cmd/gorename?go-get=1
+Parsing meta tags from https://golang.org/x/tools/cmd/gorename?go-get=1 (status code 200)
+get "golang.org/x/tools/cmd/gorename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/cmd/gorename?go-get=1
+get "golang.org/x/tools/cmd/gorename": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools?go-get=1
+Parsing meta tags from https://golang.org/x/tools?go-get=1 (status code 200)
+golang.org/x/tools (download)
+Fetching https://golang.org/x/tools/go/buildutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/buildutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/buildutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/buildutil?go-get=1
+get "golang.org/x/tools/go/buildutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/refactor/rename?go-get=1
+Parsing meta tags from https://golang.org/x/tools/refactor/rename?go-get=1 (status code 200)
+get "golang.org/x/tools/refactor/rename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/rename?go-get=1
+get "golang.org/x/tools/refactor/rename": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
+get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/loader?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/loader?go-get=1 (status code 200)
+get "golang.org/x/tools/go/loader": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/loader?go-get=1
+get "golang.org/x/tools/go/loader": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/cgo?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/cgo?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/cgo": found meta tag get.metaImport{Prefix:tus code 200)
+get "golang.org/x/tools/refactor/rename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/rename?go-get=1
+get "golang.org/x/tools/refactor/rename": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
+get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/loader?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/loader?go-get=1 (status code 200)
+get "golang.org/x/tools/go/loader": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/loader?go-get=1
+get "golang.org/x/tools/go/loader": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/cgo?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/cgo?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/cgo": found meta tag get.metaImport{Prefix:tus code 200)
+get "golang.org/x/tools/refactor/rename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/rename?go-get=1
+get "golang.org/x/tools/refactor/rename": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
+get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/loader?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/loader?go-get=1 (status code 200)
+get "golang.org/x/tools/go/loader": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/loader?go-get=1
+get "golang.org/x/tools/go/loader": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/cgo?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/cgo?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/cgo": found meta tag get.metaImport{Prefix:tus code 200)
+get "golang.org/x/tools/refactor/rename": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/refactor/rename?go-get=1
+get "golang.org/x/tools/refactor/rename": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/ast/astutil?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/ast/astutil?go-get=1 (status code 200)
+get "golang.org/x/tools/go/ast/astutil": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/ast/astutil?go-get=1
+get "golang.org/x/tools/go/ast/astutil": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/loader?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/loader?go-get=1 (status code 200)
+get "golang.org/x/tools/go/loader": found meta tag get.metaImport{Prefix:"golang.org/x/tools", VCS:"git", RepoRoot:"https://go.googlesource.com/tools"} at https://golang.org/x/tools/go/loader?go-get=1
+get "golang.org/x/tools/go/loader": verifying non-authoritative meta tag
+Fetching https://golang.org/x/tools/go/internal/cgo?go-get=1
+Parsing meta tags from https://golang.org/x/tools/go/internal/cgo?go-get=1 (status code 200)
+get "golang.org/x/tools/go/internal/cgo": found meta tag get.metaImport{Prefix::



Roc@DESKTOP-2MMHSEK MINGW64 /c/Code/GitHub/QinRoc/TechLog (gh-pages-hexo)
commit 14d4d2aded14f3c5272359f76b50eec2f02a01cc (origin/gh-pages-hexo)
Author: QinRoc <qinrocdev@gmail.com>
Date:   Fri Mar 29 18:57:02 2019 +0800

    docs: add 2 drafts

diff --git a/source/_drafts/Software-Project-Development-Specification-Publicity
-Conference.md b/source/_drafts/Software-Project-Development-Specification-Publi
city-Conference.md
new file mode 100644
index 0000000..1afaf20
--- /dev/null
+++ b/source/_drafts/Software-Project-Development-Specification-Publicity-Confer
ence.md
@@ -0,0 +1,20 @@
+---
+#Drafts are not displayed by default. You can add the --draft option when runni
ng Hexo or enable the render_drafts setting in _config.yml to render drafts.
+#https://hexo.io/docs/writing
+#https://hexo.io/docs/front-matter
+layout: draft
+title: 软件项目开发规范宣贯会反思
+date: 2019-03-29
git merge origin/gh-pages-hexo
Updating 1239b97..14d4d2a
Fast-forward
 _config.yml                                        |  11 +-
 scaffolds/draft.md                                 |  11 +
 scaffolds/post.md                                  |  11 +
 source/_drafts/Appium.md                           | 396 +++++++++++++++++++
 source/_drafts/CAA-DIF.md                          |  35 ++
 .../_drafts/One-Client-with-Multi-Git-Account.md   |  29 ++
 ...velopment-Specification-Publicity-Conference.md |  20 +
 source/_drafts/VisualCode-with-Go.md               | 425 +++++++++++++++++++++
 source/_drafts/VisualStudioCode-with-Git.md        |  14 +
 source/_drafts/Win-Linux-Dual-Sys.md               |  93 +++++
 source/_posts/Blog-1-0-0.md                        |   7 +
 11 files changed, 1049 insertions(+), 3 deletions(-)
 create mode 100644 source/_drafts/Appium.md
 create mode 100644 source/_drafts/CAA-DIF.md
 create mode 100644 source/_drafts/One-Client-with-Multi-Git-Account.md
 create mode 100644 source/_drafts/Software-Project-Development-Specification-Publicity-Conference.md
 create mode 100644 source/_drafts/VisualCode-with-Go.md
 create mode 100644 source/_drafts/VisualStudioCode-with-Git.md
 create mode 100644 source/_drafts/Win-Linux-Dual-Sys.md


```