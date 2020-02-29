# InitGitClient
Git客户端连接远程仓库配置信息


#设置用户名
git config --global user.name 'Mr-LeiLei'
#设置邮箱
git config --global user.email '1697922769@qq.com'
#查看设置
git config --list

常用命令：
	git status 查看相关文件的状态
	touch a.txt  创建一个文件

初始化本地仓库：
	1，创建文件夹
		mkdir test
	2，在test文件夹内初始化Git（创建Git仓库）-->生成一个.Git文件夹
		cd test
		git init
		创建文件：touch a.txt
	3，把文件提交到暂存区
		git add a.txt
	4，将文件从暂存区提交到仓库
		git commit -m '添加a.txt文件'
	5，修改文件
		直接打开文件修改或者命令行修改（修改完需要再次提交到仓库）
		vi：打开文件并编辑  cat：查看文件
	6，删除文件
		rm a.txt
		从Git中删除文件：git rm a.txt
		提交操作：git commit -m '描述'
	
克隆远程仓库：git clone 仓库地址
上传到GitHub：git push


解决git push错误：
	No configured push destination.
	原因：第一次push时需要网址
		$ git add --all
		$ git commit -m "提交信息"
		$ git remote add origin '远程仓库url'
		$ git push -u origin 对应远程分支名

	The requested URL returned error: 403 Forbidden while accessing
	答案：私有项目，没有权限，输入用户名密码，或者远程地址采用这种类型
	
	vi .git/config
	将[remote "origin"] url=https://github.com/用户名/仓库名.git
	修改为：[remote "origin"] url=https://用户名：密码@git.com/用户名/仓库名.git

