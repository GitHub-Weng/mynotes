git add filename
git commit -m "comment"
git status
git log
git log --pretty=short
git diff
git diff head
git branch
git branch branch-name
git checkout branch-name
git checkout -b branch-name
git checkout - //回到上一个分支

//合并分支
git merge --no-ff branch-name
git merge branch-name

git log --graph
git reset --hard   hashcode//恢复到之前的时间点

git reflog
//查看之前的命令

git commit --amend——修改提交信息

git commit -am "comment"//add and -m

git rebase -i head~2//可以选定当前分支中包含
H E A D（最新提交）在内的两个最新历史记录为对象，并在编辑器中 打开。将 6fba227 左侧的 pick 部分删除，改写为 fixup


git remote add origin git@github.com:GitHub-Weng/githubtest.git

git push -u remote master

git clone git@github.com:GitHub-Weng/githubtest.git

执行 git clone命令后我们会默认处于 master 分支下，同时系统 会自动将 origin 设置成该远程仓库的标识符。也就是说，当前本地仓库 的 master 分支与 GitHub 端远程仓库（origin）的 master 分支在内容上是 完全相同的。




git branch -a //查看当前分支的相关情况，a参数可以同时显示本地仓库和远程仓库的分支信息

git checkout -b featurec origin/featurec
//创建了一个与origin上的featurec一样的 分支，之后修改，直接push可以直接修改github上的对应分支点的内容


在 GitHub 中，很多页面都可以使用键盘快捷键。熟悉键盘操作， 能够让 GitHub 变得更加便捷。
在各个页面按下 shift ＋ / 都可以打开键盘快捷键一览表



Explore
从各个角度介绍 GitHub 上的热门软件。

Gist 功能主要用于管理及发布一些没必要保存在仓库中的代码，比
如小的代码片段等。笔者就经常把一些随便编写的脚本代码等放在 Gist 中。系统会自动管理更新历史，并且提供了 Fork 功能。另外，通过 Gist 还可以很方便地为同事编写代码示例。
在 Gist 上添加的代码示例可以嵌入博客中。当然，如果选择了语 言，还会自动添加语法高亮。详细介绍请参考附录 B。


github 界面
t键进行搜索
url中尾部的#L10-15



https://github.com/rails/rails/compare/4-0-stable...3-2-stable 



https://github.com/rails/rails/compare/master@{7.day.ago}...master


https://github.com/rails/rails/compare/master@{2013-01-01}...master



从remote中更新自己的代码
首先fork,在本地创建文件夹作为仓库，进入文件夹
然后git clone
之后为本地库设置remote，git remote add upstream//这个是自己起的名字，作用是给原仓库起名字
eg： git remote add upstream git@github.com:octocat/Spoon-Knife.git
之后就利用fetch语法从原来的仓库获取最新的数据
eg: git fetch upstream

各位在创 建特性分支，编辑源代码之前，建议先将仓库更新到这一状态。一般情 况下 master 分支都会获取最新代码，很少需要 Fork 的开发者亲自进行 修正。




发送pull request
1 fork
2 clone
3 branch //在特性分支中作业，各位请养成创建特性分支后再修改代码的好习惯。在 GitHub 上发送 Pull Request 时，一般都是发送特性分支。这样一来，Pull Request 就 拥有了更明确的特性（主题）。让对方了解自己修改代码的意图，有助 于提高代码审查的效率。
4 edit code
5 git diff to check wether have changed
6 git push origin work//[这里的work是特性分支的名字]
7 check wether the branch have been created in the github
git branch -a
8 send pull request on github





处理pull requset 请求
其他人可能只是对整个项目的某个分支进行fork，之后对这个分支的内容进行修改，再发送pull request，因此处理的步骤如下：

1 将接收方的仓库clone到本地库，若已经clone，用pull更新
2 添加远程库，git add remote sender +地址，进行fetch，git fetch sender，获得了发送方的仓库以及发送方进行修改的分支的数据(分支为work)
3 创建用于检查的分支,pr,pr与原来的自己的本地的分支一致
4 进入pr分支，将pr与work分支合并，git merge work
5 删除分支 git branch -D pr




删除github网站库中的内容：

若本地已经有了一份备份，将本地的文件删除，git status查看状态，此时出现被删除的文件，git rm 文件名, git add . , git commit -m "", git push origin master（此时你已经git remote add origin git@github.com:GitHub-Weng/mynotes.git，origin 对应的是远程库的地址，若用clone则直接默认完成这步）,
这几步下来便可以删除github库中的的文件。本地文件夹中直接删除再push是不行的，因为push上去的是本地git库中的内容，此时内地库中的缓存还有原来的文件，所以必须rm,再进行add,push，最后的push.


同样要添加也是一样，直接在本地中将文件添加是不行的，git status,git add . ,git commit -m "",git push origin master,这样才可以。

