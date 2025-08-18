暂存区：git/index 本地仓库：.git 远程仓库：存储远程分支
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
