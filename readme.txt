Git is a distributed version control system.
Git is free software distributed under the GPL.
notepad xx.txt
vi readme.txt

git check -- filename
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
git reset HEAD filename
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
git reset --hard HEAD^
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
git rm 用于删除版本库中的一个文件。
git check 使用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以还原。
git remote add origin git@github.com:Luke-Lyu/test_git.git 将本地仓库与远程仓库进行关联
git push -u origin master
git push -u origin main 默认的远程库的名字是origin，这步是把本地库的所有内容推送到远程库上。
git branch dev 创建分支
git checkout dev 移动到分支 git checkout -b xx 创建并移动到分支xx
查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>或者git switch <name>
创建+切换分支：git checkout -b <name>或者git switch -c <name>
合并某分支到当前分支：git merge <name>
删除分支：git branch -d <name>

修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；
当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场；
在master分支上修复的bug，想要合并到当前dev分支，可以用git cherry-pick <commit>命令，把bug提交的修改“复制”到当前分支，避免重复劳动。
git cherry-pick xx;可以复制一个特定的提交到当前分支;
