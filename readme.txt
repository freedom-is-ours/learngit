
Git is a distributed version contral system.
Git is free software distributed under the GPL.
---
git init //创建一个git仓库

//每次改动后提交新版本都是这两个命令，很重要
git add filename //将一个文件添加到git，可add多个文件一次提交
//如果多次改动，可以先add，一并提交
git commit -m "版本说明" // 提交变动的版本，加简要版本说明

git status //查看改动，让我们时刻掌握仓库当前的状态
git diff  //查看具体改动

//版本控制
git log //查看提交日志
git reset --hard () //退回()版本 可以加HEAD~n 或者对应的版本号，版本号万幸不需要全写
//HEAD代表当前版本 HEAD^或HEAD~1代表上一版本 HRAD~100 往上100个版本
git reflog //可以查看操作日志，可以找到过往文件的版本号

//版本退回
git checkout -- filename //让文件回到已经add到暂存区的版本（没有的话就是已经commit的版本），适用于未add的文件
git reset HEAD filename //让文件回到当前已commit的版本，适用于错误修改已经add的情况

//删除文件 cmd中rm命令和直接右键删除后
git rm filename //彻底将版本库中那个文件删掉，完后还需要commit，跟删完文件后add，commit效果一样
//如果是误删要恢复用git checkout

//远程同步到github
1.创建ssh key：
            -->Git Bash
            -->git config --global user.name "username"
            -->git config --global user.email "youremail@example.com"
            -->cd
            -->mkdir .ssh
            -->ssh-keygen -t rsa -C "youremail@example.com"
            一路回车，然后C:\users\USER\.ssh\id_rsa.pub 是公钥id_rsa.pub是你的公钥
2.在GitHub上添加ssh key ，把公钥粘贴上
3.在GitHub创建一个新的repo，与本地的同名(不同名当然是不好记啦)， 用命令行PUSH上去：
            -->git remote add origin https://github.com/账户名/仓库名.git
            -->git push -u origin master //把当前分支推送到远程的master分支，此处-u参数把这两个关联起来
//origin是远程库的默认叫法
4.此后同步只需要：
            -->git push origin master
5.从git克隆
            -->git clone git@github.com:username/reponame.git //这是利用ssh，还可以用https的，只是clone后面跟的连接不同了

//分支管理
git branch dev //创建分支dev
git switch dev 或者git checkout dev //切换到dev，，checkout命令还有版本退回的作用，注意区分
git checkout -b <name>或者git switch -c <name> //创建并切换到新的分支，switch是新版本的命令，2.23以前的版本没有
git branch //查看分支，当前分支前会有*号
//切换到dev分支后add commit就都是向dev分支提交的了
git merge dev //将dev分支合并到master上，实际上是将dev的标签改成了master，如果是fast forward的情况
git branch -d dev //-d就将dev分支删掉

//解决冲突

