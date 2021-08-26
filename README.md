# GitHub与Gitee介绍
![](https://www.runoob.com/wp-content/uploads/2015/02/git-command.jpg)
## 1. git基本概念
### workspace工作区  
就是你在电脑里能看到的目录。也包含隐藏目录，因此不同的仓库是不兼容的。
### staging area暂存区
一般存放在.git目录下的 index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
### local repository版本库/本地仓库
工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。里面东西很多
### remote repository远程仓库
github/gitee云端，一个本地仓库可以对应多个远程仓库
### local branch本地分支
分支的作用类似于时间线，当多个人一起开发时，一个人负责一个部分，因此需要展开不同的时间线，存在一个主时间线，最后时间线收束，汇聚回主时间线。
回退也方便，新建一个branch，然后在里面进行修改，改崩了就换回branch把那个删了
### remote branch远程分支
同local branch
### project项目板
GitHub 上的项目板帮助您组织工作和排列工作的优先级。 您可以为特定功能工作、全面的路线图甚至发布检查列表创建项目板。 通过项目板可以灵活地创建适合需求的自定义工作流程。项目板包括议题、拉取请求和注释，在选择的列中分类为卡片。 您可以拖放或使用键盘快捷键对列中的卡片重新排序，在不同列之间移动卡片，以及更改列的顺序。  
也就是指没啥用
### issue
也没啥用

## 2. 从零到把文件上传上去
### 1. 远端创建仓库
在GitHub/Gitee上建立新的仓库，命名为test(分支？)，获得两个Git URL

	https://gitee.com/y-zk/test.git  
	https://github.com/yinzikang/test.git  
  
### 2. 本地创建仓库
	cd test/
	git init
	touch README.md
	git add .
	git commit -m "xxxx"
    git remote -v
    git remote rm origin
    git remote add gitee https://gitee.com/y-zk/test.git
    git remote add github https://github.com/yinzikang/test.git
    git push gitee master
    git push github master


## 3. 远端有仓库，本地没有
	git clone https://gitee.com/y-zk/test.git	
	git add .
	git commit -m "xxxx"
    git push origin master

## 4. 远端、本地有同一仓库
	git add .
	git commit -m "xxxx"
    git push origin master

## 4. 部分修改仓库
### 1.部分下载  
	git clone -b branchname urlname
### 2.部分上传
网页上可以上传，但是一定时长内个数有上限

## 5. 命令详解
###`git init`
用于初始化git环境，使用当前目录作为Git仓库，然后产生一个隐藏目录.git  
###`touch README.md`
建立与该文件相同的md文件  
###`git add`
加到暂存区。  
`git add .`使git对当前目录下所有文件进行跟踪，注意add与.之间的空格。  
`git add *.c`将目录下以 .c 结尾文件提交到仓库中（add*？）  
###`git commit`
加到本地仓库。  
`git commit -m "xxxx"`xxxx为comment，关于最近一次修改的解释总结；  
linux里面为单引号，win为双引号  
###`git remote`
远程仓库操作。  
比如加上或者去掉远程仓库及其对应别名`git remote rm name1`， `git remote add name2 url2`
###`git push`
加到远程仓库并合并。  
语法`git push <远程主机名> <本地分支名>:<远程分支名>`，或`git push <远程主机名> <本地分支名>`。  
<远程主机名>、<本地分支名>、<远程分支名>都为url与master的别名，因此取什么都行，一般会初始化origin与master，如git clone url1 master1后，将主动将clone指向为url1，将master指向为master1
###`git pull`
下载远程仓库并合并。  
语法`git pull <远程主机名> <本地分支名>:<远程分支名>`，或`git push <远程主机名> <本地分支名>`。
###`git branch branchname`
创建分支命令
###`git checkout branchname`
切换分支命令
###`git branch`
列出分支基本命令
###`git merge`
分支融合
###`git branch -d branchname`
删除分支命令

## 5.软件中的关联

	