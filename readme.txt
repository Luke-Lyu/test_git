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
