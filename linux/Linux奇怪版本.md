# Linux奇怪版本

> #### 前言
>
> 在vmware中折腾安装过几个Linux发行版，有空又折腾在win和android上使用Linux。
>
> 使用过程中发现路径各自有所区别，就大致整理了一下。

## 一、WSL（Windows Subsystem for Linux）

> 因为升级成wsl2会与vmware虚拟机有冲突，我用的是wsl1
>
> 我目前用的是终端工具是windows terminal（也可以用Hyper，或者搭配vscode使用，win自带的cmd过于简陋用起来不舒服）

### 主目录~ 路径 

`/root`

### win主机的盘的路径（挂载在mnt下）

`/mnt`


### vim和zsh配置路径

```shell
/etc/vim/vimrc
/etc/zsh/zshrc
```

### 配置oh-my-zsh主题路径

```shell
 /root/.oh-my-zsh/themes/powerlevel10k.zsh-theme
```


## 二、安卓的Termux（不需root）

> 参考资料：
>
> 1. Termux 高级终端安装使用配置教程：https://www.sqlsec.com/2018/05/termux.html
>
> 2. Termux 入门教程：架设手机 Server 下载文件：https://www.ruanyifeng.com/blog/2019/07/termux-tutorial.html
>

### 主目录~ 路径

`data/data/com.termux/files/home` 

### 手机存储路径

`~/storage/shared`

### ssh连接（Linux通用，但“不完整”）

+ ##### 软件安装 

`pkg install openssh`

> 不同发行版的安装命令不同

+ #### 修改密码

`passwd`

+ ##### 查看ip地址 

`ifconfig`

> 注意！这里SSH服务监听的端口是8022。

+ ##### 查看用户名

`whoami`

- ##### 开启服务

`sshd`

+ 关闭服务

`pkill sshd`

##### win的cmd或linux用ssh连接完整命令：
`ssh -p 8022 u0_****@192.168.****`

> 这里的 * 替换为上述命令得出的用户名和ip地址

### zsh配置路径

`~/.zshrc`

配置oh-my-zsh主题路径

`~/.oh-my-zsh/themes`

## 三、Linux Deploy（需要root）

### 主目录~ 路径

和wsl一样：`/root`

### 手机存储路径

与设置的挂载路径有关，我设置的挂载点是 /sdcard - /sdcard

因此我的路径为`/sdcard`

### ssh连接

与Termux一样，但这里端口默认为22（可以修改）

### zsh配置路径

`~/.zshrc`

配置oh-my-zsh主题路径

`~/.oh-my-zsh/themes`
