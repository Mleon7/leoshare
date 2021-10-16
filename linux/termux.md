# Termux 个人

##### 前言：

参考：https://www.sqlsec.com/2018/05/termux.html#toc-heading-1

> 一定要听教程的，从https://f-droid.org/packages/com.termux/下载，不要从google play下载

### 一、基础配置

#### 软件

```shell
pkg install vim curl wget git tree -y
```

#### 存储权限

```shell
# 请求访问手机的存储权限
termux-setup-storage
```

### 二、网络

#### 端口：

```shell
# 安装nmap端口扫描神器
pkg install nmap

# 扫描本地端口
nmap 127.0.0.1
```

#### ifconfig

```bash
pkg install net-tools
```



### 三、美化

#### 下载ohmyzsh

```bash
sh -c "$(curl -fsSL https://github.com/Cabbagec/termux-ohmyzsh/raw/master/install.sh)"  
```

或

```bash
sh -c "$(curl -fsSL https://html.sqlsec.com/termux-install.sh)"  
```

**设置色彩样式**：

输入`chcolor`命令更换色彩样式，或者执行`~/.termux/colors.sh`命令

**设置字体**

运行`chfont`命令更换字体，或者执行`~/.termux/fonts.sh`命令

```bash
Enter a number, leave blank to not to change: 14
Enter a number, leave blank to not to change: 6
```

> 　当oh-my-zsh使用了agnoster主题之后，每一行路径之前都会出现 用户名@主机名 的无用信息，我们可将其隐藏。
>
> 　　直接编辑agnoster.zsh-theme主题配置文件，命令如下：
>
> 
>
> ```
> vim ~/.oh-my-zsh/themes/agnoster.zsh-theme
> ```
>
> 　　在vim打开的文件中找到以下代码行：
>
> ```
> # Context: user@hostname (who am I and where am I)``prompt_context() {`` ``if` `[[ ``"$USER"` `!= ``"$DEFAULT_USER"` `|| -n ``"$SSH_CLIENT"` `]]; then`` ``prompt_segment black ``default` `"%(!.%{%F{yellow}%}.)%n@%m"
> ```
>
> 　　将 prompt_segment black default "%(!.%{%F{yellow}%}.)%n@%m" 注释即可，即 prompt 前面加 " # " 

#### 插件

```bash
# 拷贝到 plugins 目录下
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```



```ini
plugins=(其他的插件 zsh-autosuggestions)
```

#### 修改问候语

```bash
vim $PREFIX/etc/motd
```

### 四、

#### 超级管理员身份（手机没有root）

```bash
pkg install proot -y
```

```bash
termux-chroot
```

输入`exit`可回到普通用户的文件系统。

#### 备份

去 Termux 根目录下：

```bash
cd /data/data/com.termux/files
```

备份配置文件为 termux-backup.tar.gz：

```bash
tar -zcf /sdcard/termux-backup.tar.gz home usr
```

> 这些私有目录看上去类似如下的目录：
>
> ```bash
> /data/data/com.termux 
> /sdcard/Android/data/com.termux
> /storage/XXXX-XXXX/Android/data/com.termux
> ${HOME}/storage/external-1
> ```
>
> 珍爱数据，远离私有目录。

#### 恢复

```bash
cd /data/data/com.termux/files
```

解压提取之前备份的内容，覆盖现存的文件并删除之前的备份文件：

```bash
tar -zxf /sdcard/termux-backup.tar.gz --recursive-unlink --preserve-permissions
```

操作完成重启 Termux 即可恢复数据。

### 五、

#### C语言

```bash
pkg install clang
```

```bash
clang hello.c -o hello
```

#### SSH连接

+ 安装

```bash
pkg install openssh
```

+ 设置新密码

执行 `passwd` 命令可以直接修改密码：

```bash
passwd
```

+ ##### 查看ip地址 

`ifconfig`

> 注意！这里SSH服务监听的端口是8022。

+ ##### 查看用户名

`whoami`

- ##### 开启服务

`sshd`

+ **关闭服务**

`pkill sshd`

+ **win的cmd或linux用ssh连接完整命令：**

`ssh -p 8022 u0_****@192.168.****`

> 这里的 * 看你自己的用户名和ip地址

+ **通过公私钥连接**

略

```bash
# ssh -i 私钥 用户名@主机名或者IP
ssh -i id_rsa user@hostname_or_ip
```
