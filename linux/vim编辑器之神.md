# 010.编辑器之神VIM

## 000.简单介绍

各种编辑器：vi nano emacs KWrite （i improved）

+ emacs 神之编辑器
+ VIM 编辑器之神

## 001.vim的简单使用

VIM两种模式：

1. 普通模式（命令操作模式）按**Esc**进入

    操作文件

    w write

    q quit

    > 命令模式
    >
    > 可视化模式 visual 选择文本

2. 插入模式insert（编辑的时候） 按**i**进入


## 002.移动

hjkl

+ H 左
+ L 右
+ J 下
+ k 上

## 003.翻页

+ ctrl + f 向下一页
+ ctrl + b 向上一页
+ ctrl + e 向下滚动
+ ctrl + y 向上滚动
+ shift + g (G) 尾
+ g + g 头

```shell 
:q! 不保存退出
```

## 004.不同方式编辑文本，以及跳跃单词

1. + i 光标位置的前面插入
    + a 光标位置的后面插入
    + o 直接Enter到下一行输入
2.  + x 删除光标所在字符
    + dd 删除整个一行
    + u 撤销

3. + dw 移除当前所在光标往后的单词
    + b 跳跃单词首字母
    + e 跳跃单词末字母
    + w 跳跃下一个单词的首字母

    shift + b、e、w ：大跳

## 005. 跳跃行首行尾

+ shift + 6 （^）跳跃到本行的开头
+ shift + 4 （$）跳跃到本行的末尾



- r 改光标所在字母

- R 替换

> 在普通模式里，千万别使用退格键 Backspace Delete

## 006.大括号跳跃函数段落

shift + { }

## 007.vim复制剪切粘贴

p paste

+ yw 表示复制一个单词
+ y$ 表示，从当前开始，往后复制到行末尾

> 缺点：不知道复制了啥

## 008.Visual可视化模式

1. + v
    + V 行
    + ctrl + v 矩阵选择
2. + d 删除 p 粘贴
    + gg v G 全选
    + 数字0 补全角落
    + 字母o 跳跃选中文本
    + aw 选择单词
    + ab 包含括号
    + aB 包含大括号
    + a< 包含尖括号

## 009.视图模式其他的用法

+ shift + <> 代码缩进
+ shift + ~ 字母大小写切换
+ shift + u 全部转化成小写
+ shift + U 全部转化成大写

## 010.查找和替换

 **/** 

:s/const/需替换的/替换后的/g

:%s/需替换的/替换后的/g    全局替换

:9,15s/const/let/gc    c指询问是否删除

set number

## 011.vim的基础配置

> vim .

```shell
touch .vimrc
vim .vimrc
	set syntax=on
	set tabstop=4
	set softtabstop=4
	set number 
	set enc=utf-8
	set showmatch
	
source .vimrc
```

```shell
number ++ gg 跳转到某行
```

