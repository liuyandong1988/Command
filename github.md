**工作区：** 就是一个多了.git文件的文件夹，不要想太多，就按Linux操作文件夹的方法正常操作 

**暂存区：** 暂时讲了两种操作暂存区的方法： 1.存入暂存区 git add filename git rm filename 这两条都是修改暂存区 2.递交暂存区 git commit -m "log" 别忘了正常来说一般对暂存区修改以后一定要commit一下
**版本库：**git commit以后的最终版本存入地方，git最重要的一个地方，因为只有版本库的修改才可以跟踪







# 创建仓库

1. 创建一个空目录

2. git init Git可以管理的仓库(当前目录下多了一个`.git`的目录)

3. 用命令`git add`告诉Git，把文件添加到仓库(git add readme.txt)

4. 用命令`git commit`告诉Git，把文件提交到仓库(git commit -m "wrote a readme file")

5. ```
   git add file2.txt file3.txt 提交多个文件
   git commit -m "add 3 files."
   ```



# 修改文件并提交

1. git add     &&  git  commit -m "***"
2. 历史记录，在Git中，我们用`git log`命令查看. git log --pretty=oneline 缩略版



# get the old version file

1. 使用`git reset`命令 git reset --hard HEAD^  (HEAD^, HEAD^^)
2. 恢复删除的版本 git reset --hard 1094a （需要提前记住版本号）
3. 没有记住版本号 git reflog 查看每一步的操作



# 工作区和暂存区

工作区目录下可以看到的文件， git add 把工作区中的文件添加到了暂存区；

git commit 提交更改， 把暂存区中的文件提交到了当前分支；

1. 先用`git status`查看一下状态
2. git add new_file 暂存区出现新文件
3. git commit no add file to commit



# 管理的修改而非文件

1. 修改readme文件， add
2. `git diff HEAD -- readme.txt`命令可以查看工作区和版本库里面最新版本的区别

# 撤销修改，删除

1. ```python
   $ git checkout -- readme.txt
   ```

2. 让这个文件回到最近一次`git commit`或`git add`时的状态

3. ```
   $ rm test.txt Git知道你删除了文件，因此，工作区和版本库就不一致了
   ```

4. 一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`
5. 另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本$ git checkout -- test.txt

# 添加远程库

1.  在Repository name填入×××，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库

2. 可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库

3. 我们根据GitHub的提示，在本地的×××仓库下运行命令
   
   ```
   $ git remote add origin git@github.com:michaelliao/learngit.git
   ```

4. 把本地库的所有内容推送到远程库上

   ```
   $ git push -u origin master ***第一次
   Counting objects: 20, done.
   Delta compression using up to 4 threads.
   Compressing objects: 100% (15/15), done.
   Writing objects: 100% (20/20), 1.64 KiB | 560.00 KiB/s, done.
   Total 20 (delta 5), reused 0 (delta 0)
   remote: Resolving deltas: 100% (5/5), done.
   To github.com:michaelliao/learngit.git
    * [new branch]      master -> master
   Branch 'master' set up to track remote branch 'master' from 'origin'.
   ```

5. 从现在起，只要本地作了提交，就可以通过命令

   ```
   $ git push origin master
   ```

6. 先`git pull`,但是这个命令会自动合并分支
7. 如果你确定远程分支上那些提交都不需要了，那么直接`git push origin master -f`，强行让本地分支覆盖远程分支

# 克隆远程仓

1. 用命令`git clone`克隆一个本地库
2. ```$ git clone git@github.com:liuyandong1988/gitskills.git```