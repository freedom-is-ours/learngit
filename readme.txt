this is a new file named readme
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
3.在GitHub创建一个新的repo，与本地的同名， 用命令行PUSH上去：
            -->git remote add origin https://github.com/账户名/仓库名.git
            -->git push -u origin master
