- 仓库管理，文件管理，分支管理，标签管理，远程操作
- git init是初始化本地仓库，后面可以加上你的本地的文件名称或者地址
- git 维护着三个指针，当前工作目录，缓冲区，以及最后一次的更改
	- 分别对应着三个方法
	- ![[Pasted image 20260718225754.png]]
- 如果你要将本地的仓库与远程的仓库建立分支，你需要用 git remote add 你自己给远程的仓库起的别名 远程仓库的网址
- 如果关联之后你要提交 git push -u origin master注意，这里的master是一个分支，如果，没有的话会自动创建-u是默认建立追踪关系，下次在输入的时候输入git push就可以了
- git pull origin master
- git pull 的本质就是git fetch 加上 git merge
**分支**
- 创建分支git branch  加文件就是创建分支，不加文件就是查看当前分支
- git checkout 就是切换分支 ， checkout含义是借出或者切出的意思
- git checkout -b 就是创建并且切换过去
- git branch -d 就是删除分支
- git push origin branch 就是提交分支
- git branch -a 查看当前所有分支
- 在git上面每一个分支都是权力平等的，git merge 来合成其他的分支，git diff 来查看分支的改动差异
- git merge master --allow-unrelated-histories
	- 对于diff来说，有时候报告写不下，就会有 enter 往下一行，back(b)往上一页，空格往下一页，q退出浏览
**标签**
- git log 查看所有的提交日志
- git tag 标签 提交号   
**如何回退代码**
- 如果只是某个文件写错了，你想要修改，git checkout -- <filename>会把最近一次的文件回退，放到缓冲区的不受影响。
**如果你整个项目彻底废了**，直接把远程的仓库拿过来，强行覆盖当前项目所有的文件
**git** getch orign    git reset -hard origin/**main**。




