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
	#当同一文件内相同字段的内容被修改时 将会发生冲突 需要手动合并
> 格式如下 保留、删除文件后 将标识符号删除 保存即为合并后的内容
>
	<<<<<<<<HEAD
	当前版本
	========
	分支版本
	>>>>>>>>branch


