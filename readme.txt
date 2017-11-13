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

15.分支
	a.创建分支	git branch <name>
	b.查看当前分支  git branch
	c.切换回master分支 git checkout master
	d.切换分支   	git checkout <name>
	e.创建+切换分支 git checkout -b <name>
	f.合并某分支到当前分支 git merge dev
	g.删除dev分支 git branch -d dev
	h.分支合并图 git log --graph
	i.当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

16.首先，master分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；那在哪干活呢？干活都在dev分支上，也就是说，dev分支是不稳定的，到某个时候，比如1.0版本发布时，再把dev分支合并到master上，在master分支发布1.0版本；你和你的小伙伴们每个人都在dev分支上干活，每个人都有自己的分支，时不时地往dev分支上合并就可以了。

17.把当前工作现场“储藏”起来，等以后恢复现场后继续工作 git stash

18.恢复stash内容 git stash pop

19.强行删除
如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。

20.查看远程库的信息 git remote -v

21.多人协作的工作模式
a.首先，可以试图用git push origin branch-name推送自己的修改；
b.如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
c.如果合并有冲突，则解决冲突，并在本地提交；
d.有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！
e.如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

22.标签

    命令git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id；

    git tag -a <tagname> -m "blablabla..."可以指定标签信息；

    git tag -s <tagname> -m "blablabla..."可以用PGP签名标签；

    命令git tag可以查看所有标签。

