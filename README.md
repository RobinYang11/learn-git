# learn-git
## 第一步 设置全局用户名和邮箱
	git config --global  user.name  '用户名'
 	git config --global  user.email '用户邮箱'
	git config --list  //查看 全局设置列表
## 第二步  创建本地工作区
	mkdir git-test
	touch index.html
## 第三步 初始化工作区
	git init 这个命令是把本地目录初始化为一个git 工作区
## 第四步 把文件添加到暂存区
	git add index.html
## 第五步 然后提交到master 分支
	git commit 
	 在vi 编辑器中按 i 插入内容，然后ESC ，再输入":wq"就可以退出并保存
