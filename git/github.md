#git
1. 安装
>sudo apt-get install git (ubuntu && debian)
官网下载源码安装：
>./config
>make
>sudo make install
2. 设置git的名字和邮箱
>$ git config --global user.name "Your Name"
>$ git config --global user.email "email@example.com"
3. 初始化仓库
>(base) lz@Zeng-Ubuntu:~/test$ git init
已初始化空的 Git 仓库于 /home/lz/test/.git/
.git，这个目录是Git来跟踪管理版本库
只能跟踪文本文件的改动
4. 用命令git add告诉Git，把文件添加到仓库：
>git add readme.txt
5. 用命令git commit告诉Git，把文件提交到仓库：
>git commit -m "wrote a readme file"
    -m后面输入的是本次提交的说明
为什么Git添加文件需要add，commit一共两步呢？
因为commit可以一次提交很多文件，所以你可以多次add不同的文件。
6. git status 命令可以让我们时刻掌握仓库当前的状态
7. git diff 显示修改前后的差异 git diff HEAD -- readme.txt
8. git log 显示提交日志 git log --pretty=oneline
HEAD：当前版本
HEAD^:上一个版本
HEAD^^:再上一个版本
HEAD～n：第前n个版本
9. 版本回退
>git reset --hard HEAD~n
>git reset --hard d68013(版本号)
10. git reflog 记录每一次命令
11. 暂存区、工作区和版本库
文件夹目录：工作区
目录下的.git文件夹：版本库
在.git文件夹下的index（或stage）称为：暂存区
              master：自动创建的第一个分支
              head：master的一个指针
              ![](./2.png)
              ![](./0.jpeg)
              git add 之后
              ![](./1.jpeg)
              git commit之后
              ![](./2.jpeg)

12. 撤销修改
 >git checkout -- readme.txt 暂存区前
 >git reset HEAD <file>  暂存区后版本库前
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交版本回退
13. 删除文件
>rm wenjian.txt
>git rm wenjain.txt
>git commit
误删还原：git checkout -- test.txt
14. 创建ssh
>ssh-keygen -t rsa -C "youremail@example.com"
15. 将本地仓库推到github
关联远程仓库
>git remote add origin git@github.com:Spirit-style/OS.git
推送master分支所有内容
>git push -u origin master

或在本地新建仓库再推到github
```
echo "# OS" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:Spirit-style/OS.git
git push -u origin master
```
>git push origin master

16. 从远程仓库克隆
>git clone git@github.com:Spirit-style/OS.git

17. 创建分支
> git checkout -b lz    -b：创建并切换
或
>git branch dev
>git checkout dev
18. 查看分支
>git branch
19. 合并分支
>git merge dev 合并指定分支到当前分支
20. 删除分支
>git branch -d dev
21. 
Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容

```

   查看分支：git branch
   创建分支：git branch <name>
   切换分支：git checkout <name>
   创建+切换分支：git checkout -b <name>
   合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>
开始一个工作区（参见：git help tutorial）
   clone      克隆一个仓库到一个新目录
   init       创建一个空的 Git 仓库或重新初始化一个已存在的仓库

在当前变更上工作（参见：git help everyday）
   add        添加文件内容至索引
   mv         移动或重命名一个文件、目录或符号链接
   reset      重置当前 HEAD 到指定状态
   rm         从工作区和索引中删除文件

检查历史和状态（参见：git help revisions）
   bisect     通过二分查找定位引入 bug 的提交
   grep       输出和模式匹配的行
   log        显示提交日志
   show       显示各种类型的对象
   status     显示工作区状态

扩展、标记和调校您的历史记录
   branch     列出、创建或删除分支
   checkout   切换分支或恢复工作区文件
   commit     记录变更到仓库
   diff       显示提交之间、提交和工作区之间等的差异
   merge      合并两个或更多开发历史
   rebase     在另一个分支上重新应用提交
   tag        创建、列出、删除或校验一个 GPG 签名的标签对象

协同（参见：git help workflows）
   fetch      从另外一个仓库下载对象和引用
   pull       获取并整合另外的仓库或一个本地分支
   push       更新远程引用和相关的对象
```