# git使用
##linux  命令
**##初始化**

1.git init在本地创建git文件夹

***直接在github上创建仓库再拉取到本地会更简单，而且不会因README勾错而出现版本冲突***

2.git config user.name "name"

gti config user.email "e@mail.com"输入信息

***邮箱必须对应gtihub账号否则提交代码可能会被拒绝***

3.touch 名字.md创建文件

echo"内容">名字.md写入内容

echo "第二行" >> readme.md添加内容

**##日常操作**

1.git add file.txt — 暂存单个文件

git add . — 暂存所有修改

git add *.js — 暂存所有 .js 文件

2.git status 查看状态

3.git diff --staged比较缓存区和上一次之间的改动

4.git commit -m"你做了什么"提交文件到本地，就是电脑的文件夹

5.git log -n 3查看最近三条历史
git log --oneline一行一条历史

6.git restore readme.md取消本次修改

git restore --staged readme.md保留修改并撤出暂存

git restore --staged --worktree readme.md回到最后一次提交的状态

git restore --source=HEAD1 readme.md把上一次提交里的文件，直接拉到现在的工作区里

注：HEAD 代表当前最新提交，HEAD1 代表上一次提交，HEAD2 是上两次，依此类推

***提交指提交到本地仓库，以上指令基本都能在vscode上实现，且不用代码，但是可以在终端或git自带的程序使用。使用agent返回原先版本可以直接找相应提交，复制提交哈希再给ai***

**##分支操作**

1.git branch列出所有分支
git branch dev创建名为 dev 的新分支
git branch -d dev删除分支

***vscode可以直接在本地创建分支，记住要推送，删除分支时要把origin也删掉，git不允许删除当前所在的分支，删除前要切换所在分支***

2.git checkout -b dev或git switch -c dev直接创建dev并切换分支
git checkout dev或git switch dev切换分支

3.gti switch main
gti merge dev合并代码，dev是被合并的一方

**##远程协作**

1.SSH KEY

ssh-keygen -t rsa -C "your@email.com或者写ssh-keygen -t rsa -b 4096 -C "your@email.com  后者有更长的密钥长度

*vscode会询问保存位置和使用密码，一般不设使用密码，否则每次调用都要输密码*

cat ~/.ssh/id_rsa.pub复制公钥

GitHub → Settings → SSH and GPG keys → New SSH key → 粘贴公钥

2.'git remote add 名字 URL'  连接远端仓库

'git push  分支名'  把本地推送到远端

3.'git clone URL'  克隆仓库

4.'git fetch 仓库名'  查看远端更新内容，但不覆盖本地代码

5.'git pull 仓库名 分支名'  拉取仓库并覆盖

***以上还是能用vscode简易执行***

**##多人协作**

若没有权限，要先creat fork复制地址，之后在本地复制一份项目，创建一个新分支再进行修改和编写，修改后将母项目代码进行同步，若有冲突要在分支上修改好，若无则推送到github上再pull request，经管理员审核后才能合并到main

有权限也不能直接push到main,仍需要在分支同步代码，修改冲突，再经项目经理审核后并入主干