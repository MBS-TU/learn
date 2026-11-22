# git使用
##linux  命令
**##初始化**
1.git init在本地创建git文件夹
***直接在github上创建仓库再拉取到本地会更简单，而且不会因README勾错而出现版本冲突***
2.git config user.name "name"
gti config user.   email "e@mail.com"输入信息
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
git restore --source=HEAD~1 readme.md把上一次提交里的文件，直接拉到现在的工作区里
注：HEAD 代表当前最新提交，HEAD~1 代表上一次提交，HEAD~2 是上两次，依此类推
***提交指提交到本地***
***以上指令基本都能在vscode上实现，且不用代码，但是可以在终端或git自带的程序使用***
