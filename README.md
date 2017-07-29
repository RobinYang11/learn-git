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
## 其他常用 git 命令 
	git status 查看当前目录里面文件的状态
	git log 查看提交日志
	git mv 修改添加到版本库文件的名称   eg： git mv my.js main.js 
	mv linux 系统中mv 不同的是，git mv 不能修改 未添加到版本库里的文件
	git rm 删除 已经添加到版本库里面的文件

##　Git reset 　

### 作用—————— 1.文件从暂存区回退到工作区 2. 版本回退 　　　　
* git reset HEAD filename ：回退文件，将文件从暂存区回退到工作区 　//也可以使用 git reset filename
* git reset HEAD^ ：回退版本，一个^表示一个版本，可以多个，另外也可以使用 git reset HEAD～n这种形式。
- （1） soft 参数：git reset --soft HEAD～1 意为将版本库软回退1个版本，所谓软回退表示将本地版本库的头指针全部重置到指定版本，且将这次提交之后的所有 - 变更都移动到暂存区
-	（2） 默认的mixed参数：git reset HEAD～1 意为将版本库回退1个版本，将本地版本库的头指针全部重置到指定版本，且会重置暂存区，即这次提交之后的所有变更都移动到未暂存阶段
-	（3） hard参数：git reset --hard HEAD～1 意为将版本库回退1个版本，但是不仅仅是将本地版本库的头指针全部重置到指定版本，也会重置暂存区，并且会将工作区代码也回退到这个版本    
## git branch 分支
- git branch 查看当前分支
- git branch robin 创建robin分支
- git checkout robin 切换到robin 分支
## git merge 合并分支
- git merge dev  将dev 分支合并到当前分支，当前分支一般是master 分支
- git diff 分支1..分支2  比较分支1 和分支2 的不同
## 如何把本地库和github上面的仓库管理起来
- git remote add origin <gitHub仓库url> 一定要记着如果github上面的仓库里面有readme.md，要执行如下命令
	 git pull --rebase origin master 如果没有，则在创建本地库的时候要创建一个readme.md ，然后git add ，再git commit 到临时版本库里面。
# 特别重要的提示，在第一使用github是要配置github 权限
- 1.ssh-keygen -t rsa -C "your@email.com"
- 2.接着出现：
	Generating public/private rsa key pair.
	Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):
	 接着回车
	 然后系统会自动在你点到的administrator文件夹下的.ssh文件夹下生成两个文件，id_rsa和id_rsa.pub，用记事本打开id_rsa.pub
	 复制里面的的内容到你的github ssh帐号管理里面添加这个sshkey就可以了。
	 
