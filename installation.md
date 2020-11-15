# GitBook安装
下面介绍在本地如何安装 GitBook，如果不需要本地调试 & 不需要获得生成的 html 文件，可以直接使用 [官网](https://www.gitbook.com/) 提供的服务。
<!-- toc -->

## 环境要求

* NodeJS(v4.0.0及以上，推荐[v10.21.0](https://npm.taobao.org/mirrors/node/latest-v10.x/))

如果本地已有版本，推荐安装nvm：https://www.jianshu.com/p/6249d1d24914

``` bash
# nvm: https://github.com/creationix/nvm
 curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```

`vim ~/.bashrc` 写入下面代码:
``` bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

``` bash
source ~/.bashrc

NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node  nvm i 10.21.0 
nvm uninstall 10.21.0     // 移除 node 
nvm use 10.21.0            // 使用 node
nvm ls                   // 查看目前已安装的 node 及当前所使用的 node
nvm ls-remote            // 查看目前线上所能安装的所有 node 版本
nvm alias default 10.21.0  // 使用 10.21.0  作为预设使用的 node 版本
```

## 通过NPM安装
运行下面的命令进行安装
```bash
npm install gitbook-cli -g
```
其中`gitbook-cli`是gitbook的一个命令行工具, 通过它可以在电脑上安装和管理gitbook的多个版本.

## 编辑书籍
gitbook 官方已经提供了一个本地的[编辑器](https://www.gitbook.com/editor/osx), 使用它可以方便的编写书籍(不需要手动的写SUMMARY.md), 并且支持windows、mac、linux 三种平台, 所以强烈建议使用编辑器编写书籍.

## 预览书籍
使用下列命令会运行一个服务器, 通过`http://localhost:4000/`可以预览书籍
```bash
gitbook serve
```
运行该命令后会在书籍的文件夹中生成一个 `_book` 文件夹, 里面的内容即为生成的 html 文件.
我们可以使用下面命令来生成网页而不开启服务器
```bash
gitbook build
```
