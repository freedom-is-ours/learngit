this is a new file named readme
Git is a distributed version contral system.
Git is free software distributed under the GPL.
---
git init //创建一个git仓库

//每次改动后提交新版本都是这两个命令，很重要
git add  //将一个文件添加到git，可add多个文件一次提交
git commit -m "版本说明" // 提交变动的版本，加简要版本说明

git status //查看改动，让我们时刻掌握仓库当前的状态
git diff  //查看具体改动

//版本控制
git log //查看提交日志
git reset --hard () //退回()版本 可以加HEAD~n 或者对应的版本号，版本号万幸不需要全写
//HEAD代表当前版本 HEAD^或HEAD~1代表上一版本 HRAD~100 往上100个版本
git reflog //可以查看操作日志，可以找到过往文件的版本号
