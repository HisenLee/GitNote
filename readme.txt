1.git init
2.commit file
	git add readme.txt
	git commit -m "wrote a readme file"
3.git status
4.git diff readme.txt
5.git log || git log --pretty=oneline
6.用HEAD表示当前版本，也就是最新的提交;上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100
7.git reset --hard HEAD^ || git reset --hard <commitId>
8.git reflog查看命令历史
9.Working Directory & Stage 工作区和暂存区
	a.git add把文件添加进去，实际上就是把文件修改添加到暂存区
	b.git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。
	c.建Git版本库时，Git自动为我们创建了唯一一个master分支，所以git commit就是往master分支上提交更改,需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。
10.git checkout -- readme.txt 撤销
11.git rm readme.txt; git commit -m "delete file"
12.关联Github:[远程库的名字就是origin，这是Git默认的叫法]
 git remote add origin https://github.com/HisenLee/gitnote.git
13.推送到远程[把当前分支master推送到远程]
 git push -u origin master[第一次推送master分支时，加上-u参数]
 git push origin master
14.git clone git@github.com:HisenLee/gitnote.git克隆一个本地库


