# Idea整合github #
idea集成了git可以方便的进行版本控制
### 规则文件 ###

- 规则文件的配置可以仅将项目代码、部署相关的文件进行git管理
 - 创建规则文件git.ignore
 - 为方便引用 放置在用户目录下
 - 在.gitconfig中引用规则文件配置

### 文件示例 ###
	# Compiled class file
	*.class
	
	# Log file
	*.log
	
	# BlueJ files
	*.ctxt
	
	# Mobile Tools for Java (J2ME)
	.mtj.tmp/
	
	# Package Files #
	*.jar
	*.war
	*.nar
	*.ear
	*.zip
	*.tar.gz
	*.rar
	
	# virtual machine crash logs, see http://www.java.com/en/download/help/error_hotspot.xml
	hs_err_pid*
	
	.classpath
	.project
	.settings
	target
	.idea
	*.iml


----------
	[core]
		excludesfile = C:/Users/16667/git.ignore

## Idea ##
1. File>settings>Version Control>Git 
2. 定位到git安装目录下的bin\git.exe
3. 为项目创建git版本管理
 - VCS>Import into Version Control>Create Git Repository
 - 在项目根目录下点ok
4. 其余所有命令 找Git 文件右键或Idea右下角
5. 可以通过左下角的Git查看分支和日志



### github登录 ###
github>settings>Developer settings>Personal access tokens>Generate new token

输入token名称 所有权限勾选表示和登录同等权限
复制一串码保存在本地！！！刷新既无



