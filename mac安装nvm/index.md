# mac安装nvm切换Node版本


# nvm 切换不同版本的 node

最近项目中出现了一个问题，就是 node-sass 这个包一直安装失败。后来发现电脑中的 node.js 的版本太高导致。node-sass 是不支持 node16 以上的版本的。

可以通过 nvm 在电脑上切换不同版本的 node.js

安装方式：

### 1.在 vscode 中打开终端，下载安装包：（最好使用流量下载）

```
sudo curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

### 2. 刷新使其全局生效：

正常安装好之后，nvm 会自动在 mac 电脑的全局配置文件中，配置好相应的环境变量

位置为：~/.bash_profile

内容为：

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

上面的内容无需操作，但是此时环境变量并没有生效，我们需要刷新环境变量：执行如下命令

```
source ~/.bash_profile
```

### 3.验证生效

```
nvm -v
```

此时如果正确打印出版本号，代表已经安装成功。

![截屏2023-03-07 09.16.32](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-07%2009.16.32.png)

### 4.常用命令

nvm 常用命令 nvm install stable ## 安装最新稳定版 node，当前是 node v9.5.0 (npm v5.6.0)

nvm install <version> ## 安装指定版本，可模糊安装，如：安装 v4.4.0，既可 nvm install v4.4.0，又可 nvm install 4.4

nvm uninstall <version> ## 删除已安装的指定版本，语法与 install 类似

nvm use <version> ## 切换使用指定的版本 node

nvm ls ## 列出所有安装的版本

nvm ls-remote ## 列出所有远程[服务器](https://cloud.tencent.com/product/cvm?from=10680)的版本（官方 node version list）

nvm current ## 显示当前的版本

nvm alias <name> <version> ## 给不同的版本号添加别名

nvm unalias <name> ## 删除已定义的别名

nvm reinstall-packages <version> ## 在当前版本 node 环境下，重新全局安装指定版本号的 npm 包

### 5. 举例：

我需要使用 node14 版本：

nvm install 14 #等待安装结束

nvm use 14

### 6.注意事项

如果使用过程中，又出现 nvm command not found，重新执行如下命令：

source ~/.bash_profile

![截屏2023-03-07 09.18.46](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/%E6%88%AA%E5%B1%8F2023-03-07%2009.18.46.png)

