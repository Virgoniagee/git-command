# 本地仓库 #
## git设置 ##
    #设置当前管理仓库的用户 和github账号无关
    
    #设置用户 标识当前是谁在操作git
    $ git config --global user.name "[当前仓库管理员]"
    #设置邮箱 可以是虚拟的 不会去验证
    $ git config --global user.email "[***@**.com]"
    #查看当前本地用户管理信息 global【/system/list】
    $ git config --global --list

## 在本地创建 ##
	#创建本地仓库
	$ git init     //在当前bash目录下生成.git文件夹 别改
	#查看当前.git同级目录下各文件的提交状态
	$ git status
	#把本地文件提交到本地仓库缓存区
	$ git add [文件名]
	#把缓存提交到本地库
	$ git commit -m "提交说明" [文件名]
	//将获得一个版本号
	#查看版本信息
	$ git reflog
	#详细的版本信息
	$ git log
	
	#修改文件后 需要再次add后commit 每次commit后都会生成一个新的版本号
	git reset --hard [版本号]



## 在本地管理 ##
### 分支管理 ###
	#分支管理 方便项目分模块和功能开发 可以同时并行开发项目
	#创建分支
	$ git branch [分支名]
	#查看分支
	$ git branch -v
	#切换分支
	$ git checkout [分支名]
	
	#本地内的分支指针被保存在\.git\refs\heads下

### 合并分支 ###
	#将某分支合并到当前HEAD（当前）分支上
	$ git merge [需要被合并的分支版本]


> 在同一文件同一位置 冲突本质上应该是指 branch1和branch2都是基于同一个版本进行开发 branch1和branch2中分别修改了该版本号中的一些内容 并分别提交形成了新的版本号 此时需要把branch2中的修改内容合并到branch1中 那么需要对branch1和branch2中所有不同的地方手动选择合并

**当同一文件内相同字段的内容被修改时 将会发生冲突 需要手动合并**
> 格式如下 保留、删除文件后 将标识符号删除 保存即为合并后的内容
>
> <<<<<<<<HEAD
> 当前版本
> ========
> 分支版本
>
> >>>>>>>branch

	#手动解决冲突后 需要add - commit commit时不能指明文件名 
	#git不知道当前commit的版本是哪一个


# 远程仓库 #
## 创建远程仓库 创立连接 ##
	#查看当前所有远程地址别名
	$ git remote -v
	#在本地为远程仓库取别名
	$ git remote add [别名] [http://....]
## 托管中心拖取 ##
	#public 远程库的克隆 不需要登录
	#拉取代码、初始化本地库、创建别名(origin)
	$ git clone [http://....]
	
	#拉取版本更改的部分到本地库
	#自动提交本地库
	$ git pull [别名/远程地址] [分支]
## 团队开发 ##
	#非团队人员不能直接push分支到远程库
	#负责人github>settings>manage access>invite a collaborator
	#邀请github账号加入团队
	#被邀请人在邀请函地址同意
	
	#推送分支
	$ git push [别名/远程地址] [分支]
	
	#拉取
	$ git pull [别名/远程地址] [分支]

## 非团队人员开发 ##
	#拉取
	$ git clone [http://....]
	#直接提交 原本的库地址不会改变 仅改变本人的远程库
	$ git push [别名/远程地址] [分支]
	#使用pull request
	#等待团队合并

# SSH免密登录 #
必须在本地生成.shh文件夹 其内有shh密钥

	#生成ssh 表示为某用户生成ssh加密协议
	$ ssh-keygen -t rsa -C [***@**.com]
	#三次回车 将生成.shh文件夹及其下两个密钥（公/私）
	$ c:
	$ cd C:\Users\[电脑用户]\.ssh
	$ cat id_rsa.pub
	#将内容复制到github的settings>SSH and GPG keys
	#并添加

SHH免密登录 可以不用远程操控时验证登录

