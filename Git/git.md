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

