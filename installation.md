# GitBook安装
下面介绍在本地如何安装 GitBook，如果不需要本地调试 & 不需要获得生成的 html 文件，可以直接使用 [官网](https://www.gitbook.com/) 提供的服务。
<!-- toc -->

最终安装的版本：
``` bash
$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

## 环境要求

* NodeJS(v4.0.0及以上)， 推荐[v10.21.0](https://npm.taobao.org/mirrors/node/latest-v10.x/) ， 其他版本可能会不兼容。gitbook已经不更新了。

如果本地已有版本，推荐安装nvm：https://www.jianshu.com/p/6249d1d24914

``` bash
# nvm: https://github.com/nvm-sh/nvm
 curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
 
 # fast by gitee with 52fhy
 curl -o- https://gitee.com/52fhy/nvm/raw/v0.39.1_gitee/install.sh | bash
```

默认会在系统的bash配置里写入环境变量，新建一个窗口就可以使用nvm命令了。如果没有生效，可以按安装提示受到设置环境变量:
``` bash
=> Appending nvm source string to /home/yjc/.zshrc
=> Appending bash_completion source string to /home/yjc/.zshrc
=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.config/nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

接着就可以正常使用nvm了：
``` bash
# 设置NVM下载加速
NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node  nvm i 10.21.0 

# 常用命令
nvm i 10.21.0  // 安装nodejs 10
nvm use 10.21.0            // 使用 node
nvm ls                   // 查看目前已安装的 node 及当前所使用的 node
nvm ls-remote            // 查看目前线上所能安装的所有 node 版本
nvm alias default 10.21.0  // 使用 10.21.0  作为预设使用的 node 版本
nvm uninstall 10.21.0     // 移除 node 
```

## 通过NPM安装
运行下面的命令进行安装gitbook-cli
```bash
npm config set registry https://registry.npm.taobao.org
npm install gitbook-cli -g
```
其中`gitbook-cli`是gitbook的一个命令行工具, 通过它可以在电脑上安装和管理gitbook的多个版本.

此时打印gitbook版本：
```
gitbook -V               
CLI version: 2.3.2
Installing GitBook 3.2.3
/
```

提示正在安装gitbook。加速安装方法：
``` bash
wget https://gitee.com/52fhy/gitbook-use/attach_files/963279/download/gitbook_3.2.3.tar.gz
tar zxvf gitbook_3.2.3.tar.gz -C ~/
```

## 编辑书籍
可以使用vscode、typora等支持markdown的工具编辑。
gitbook 项目结构示例：
``` bash
wegt https://gitee.com/52fhy/gitbook-use/attach_files/962871/download/gitbook-example.zip
```

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

生成epub、pdf:
```
gitbook epub
gitbook pdf
```

生成epub、pdf需要系统安装有calibre: https://calibre-ebook.com/download
```
# linux 通用
sudo -v && wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sudo sh /dev/stdin

# ubuntu 版本可能比较老
sudo apt install calibre
```


