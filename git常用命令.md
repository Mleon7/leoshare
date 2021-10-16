## 前言

这两天在学廖雪峰老师的git教程，现在稍微总结一下并实践。

廖雪峰的git教程：

https://www.liaoxuefeng.com/wiki/896043488029600

廖雪峰总结的git命令：

https://liaoxuefeng.gitee.io/resource.liaoxuefeng.com/git/git-cheat-sheet.pdf

## 常用:

### 初始化

`git init`

### 查看

##### 	查看状态

		git status

##### 	查看具体修改内容

		git diff`

##### 	查看分支

		git branch

##### 	查看标签

		git tag

##### 	查看提交历史

		git log
		git log --pretty=oneline
		git log --graph

##### 	查看命令历史

		git reflog

### 更新

##### 添加所有文件到暂存区

	git add .

##### 把暂存区的所有内容提交到当前分支

	git commit -m "说明"

##### 更新本地仓库

	git pull

##### 更新远程仓库

	git push origin master
	git push 名叫origin的远程库 分支名

## github

#### 创建SSHkey

	ssh-keygen -t rsa -C "youremail@example.com"

#### 克隆远程仓库

	https://gitee.com/liaoxuefeng/learngit.git

#### 更新远程库

	git push -u origin master
	由于远程库是空的，我们第一次推送master分支时，加上了-u参数
	git push origin master

#### 关联远程连接库

	git remote add gitee git@gitee.com:liaoxuefeng/learngit.git
	git remote add 远程库名称 ssh

#### 查看远程连接状态

	git remote -v

#### 删除远程连接

	git remote rm origin

## 同步

https://scofieldwyq.github.io/2016/02/29/git%E4%BB%8E%E8%BF%9C%E7%A8%8B%E5%BA%93%E5%90%8C%E6%AD%A5%E5%88%B0%E6%9C%AC%E5%9C%B0%E4%BB%93%E5%BA%93/



## 大文件

https://git-lfs.github.com/

