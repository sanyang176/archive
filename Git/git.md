暂存区：git/index 本地仓库：.git 远程仓库：存储远程分支 标签：标识比较重要的commit
git init 初始化git仓库<br />
git init [projectname] 新建一个目录，将其初始化为git仓库<br />
git clone [url] 从远程仓库复制代码<br />
git config --list 显示git配置<br />
git config -e [--global] 编辑git配置文件<br />
设置提交本地代码时的提交记录:<br />
git config [--global] user.name "[name]"<br />
git config [--global] user.email "[email address]"<br />
git add [file1] [file2] ...添加本地文件到暂存区<br />
git add [dir]添加指定目录到暂存区，包括子目录<br />
git add -p 对于同一个文件的多处变化，可以实现分次提交<br />
git rm [file1] [file2] ... 删除工作区文件，并且将这次删除放入暂存区<br />
git rm --cached [file] 停止追踪指定文件，但该文件会保留在工作区<br />
git mv [file-original] [file-renamed] 改名文件，并且将这个改名放入暂存区<br />
git commit -m [message] 提交暂存区代码到本地仓库，message为提交信息<br />
git commit [file1] [file2] ... -m [message] 提交暂存区文件到仓库区<br />
git commit -a 提交上次commit之后的代码变化到本地仓库<br />
git commit -v 提交时显示所有diff信息<br />
git commit --amend -m [message] 使用新提交替代上一次提交<br />
git commit --amend [file1] [file2] ... 使用新提交文件替代上一次提交<br />
git branch 列出所有本地分支<br />
git branch -r 列出所有远程分支<br />
git branch -a 列出所有本地分支和远程分支<br />
git branch [branch-name] 新建名字为branch-name的分支，但是不切分支<br />
git checkout -b [branch]新建branch分支，并切换分支<br />
git branch [branch] [commit] 新建一个分支，指向指定commit<br />
git branch --track [branch] [remote-branch] 新建一个分支，指向远程分支<br />
git checkout [branch-name] 切换到指定分支，并更新工作区<br />
git checkout - 切换到上一个分支<br />
git branch --set-upstream [branch] [remote-branch] 建立追踪关系，在现有分支与指定的远程分支之间<br />
git merge [branch] 合并指定分支到当前分支<br />
git cherry-pick [commit] 选择一个commit，合并进当前分支<br />
git branch -d [branch-name] 删除分支<br />
删除远程分支：<br />
git push origin --delete [branch-name]<br />
git branch -dr [remote/branch]<br />
git tag 列出所有tag<br />
git tag [tag] 新建一个tag在当前commit<br />
git tag [tag] [commit] 新建一个tag在指定commit<br />
git tag -d [tag] 删除本地tag<br />
git push origin :refs/tags/[tagName] 删除远程tag<br />
git show [tag] 查看tag信息<br />
git push [remote] [tag]  提交指定tag<br />
git push [remote] --tags 提交所有tag<br />
git checkout -b [branch] [tag] 新建一个分支，指向某个tag<br />
git status 显示有变更的文件<br />
git log 显示当前分支的版本历史<br />
git log --stat 显示commit历史，以及每次commit发生变更的文件<br />
git log -S [keyword] 搜索提交历史，根据关键词<br />
git log [tag] HEAD --pretty=format:%s 显示某个commit之后的所有变动，每个commit占据一行<br />
git log [tag] HEAD --grep feature 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件<br />
git log --follow [file] 显示某个文件的版本历史，包括文件改名<br />
git whatchanged [file] 显示某个文件的版本历史，包括文件改名<br />
git log -p [file] 显示指定文件相关的每一次diff<br />
git log -5 --pretty --oneline 显示过去5次提交<br />
git shortlog -sn 显示所有提交过的用户，按提交次数排序<br />
git blame [file] 显示指定文件是什么人在什么时间修改过<br />
git diff 显示暂存区和工作区的差异<br />
git diff --cached [file] 显示暂存区和上一个commit的差异<br />
git diff HEAD 显示工作区与当前分支最新commit之间的差异<br />
git diff [first-branch]...[second-branch] 显示两次提交之间的差异<br />
git diff --shortstat "@{0 day ago}" 显示今天你写了多少行代码<br />
git show [commit] 显示某次提交的元数据和内容变化<br />
git show --name-only [commit] 显示某次提交发生变化的文件<br />
git show [commit]:[filename] 显示某次提交时，某个文件的内容<br />
git reflog 显示当前分支的最近几次提交<br />
git fetch [remote] 同步远程分支<br />
git remote -v 显示所有远程仓库<br />
git remote show [remote] 显示所有远程仓库<br />
git remote add [shortname] [url] 增加新的远程仓库，并命名<br />
git pull [remote] [branch] 取回远程仓库的变化，与本地分支合并<br />
git push [remote] [branch] 上传本地分支到远程仓库<br />
git push [remote] --force 强行推送当前分支到远程仓库，即使有冲突<br />
git push [remote] --all 推送所有分支到远程仓库<br />
git checkout [file] 恢复暂存区的指定文件到工作区<br />
git checkout [commit] [file] 恢复某个commit的指定文件到暂存区和工作区<br />
git checkout . 恢复暂存区的所有文件到工作区<br />
git reset [file] 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变<br />
git reset --hard 重置暂存区与工作区，与上一次commit保持一致<br />
git reset [commit] 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变<br />
git reset --hard [commit] 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致<br />
git reset --keep [commit] 重置当前HEAD为指定commit，但保持暂存区和工作区不变<br />
git revert [commit] 新建一个commit，用来撤销指定commit,后者的所有变化都将被前者抵消，并且应用到当前分支<br />
git stash 储存一下当前暂存区代码，回滚到上次提交<br />
git stash pop 加载最顶部的（最新的）stash，并移除该stash<br />
git archive 生成一个可供发布的压缩包<br />
