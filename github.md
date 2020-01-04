1. 创建一个空目录

2. git init Git可以管理的仓库(当前目录下多了一个`.git`的目录)

3. 用命令`git add`告诉Git，把文件添加到仓库(git add readme.txt)

4. 用命令`git commit`告诉Git，把文件提交到仓库(git commit -m "wrote a readme file")

5. ```
   git add file2.txt file3.txt 提交多个文件
   git commit -m "add 3 files."
   ```



修改文件并提交

1. git add     &&  git  commit -m "***"
2. 历史记录，在Git中，我们用`git log`命令查看. git log --pretty=oneline 缩略版



get the old version file

1. 使用`git reset`命令 git reset --hard HEAD^  (HEAD^, HEAD^^)





