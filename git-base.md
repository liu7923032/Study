# git 学习

## git 命令

 * git status : 查看当前仓库中文件的状态。
 * git status -s : 文件状态的简写（M - 修改， A - 添加， D - 删除， R - 重命名，?? - 未追踪）。
 * git add <文件名> ：将后方紧跟的文件进行暂存，以便commit使用。
 * git reset HEAD <文件名> : 将已经暂存的文件进行撤销，回到未暂存的状态。
 * git checkout -- <文件名> ：撤销对尚未暂存文件的修改，该操作不可逆，慎用。
 * git commit -a : 对那些被修改的文件单尚未暂存和提交的文件进行暂存和提交。注意：对未暂存的新增文件无效。
 * git commit : 对暂存区的文件进行提交到本地仓库。
 * git push : 将本地仓库已经提交的内容发布到远端。


## git clone 

第一次听到git就是在github兴起的时候，因为有很多优秀的开源项目都放在github上，要想提升自己的开发水准,一定要多看别人的优秀项目.那么首先我们在看项目的的时候,需要将项目下载下来,所以就要下载项目源码，第一个git命令就来了，来看一下如何下载源码吧。

`   git clone https://github.com/vuejs/vue.git`

## git add --<文件名>

当你有一天看到别人的源码有问题或者需要添加某种功能的时候，你会提交代码，那么你就会用到git add 命令，它的作用的将你修改的文件暂存到本地，如下例子

`   git add xxx.cs `

如果你变更的代码很多可以一次性暂存全部文件

`   git add .`

## git checkout -- <文件名> 

时光回溯,如果你想放弃自己修改的内容,在windows 系统中我们一般用ctrl+z ，而在git中我们可以用git checkout xxx.cs命令来进行内存撤销

`   git checkout -- xxx.cs`

## git status 

通过上面的几个命令，我们可以将修改的内容进行保存了，此时我们如果想知道项目文件的状态，那么就是用status,如果对git熟悉了后，可以带-s参数，git会提供简单的信息


`   git status -s `

## git commit -m '内容'

前面两个命令，都是临时性的保存文件，如果我们要永久保存的话，我们需要进行 commit ，commit后就会将我们改动的内容保存到本地的git库中了

`   git commit -m '说明'`

如果想直接对新增的文件进行提交可以带-a参数

`   git commit -a -m '说明'`

## git reset HEAD 文件名

git add 文件命令执行后,有时候需要还原状态，使用git reset HEAD XXX.cs 可以回到暂存前的状态

`   git reset HEAD xxx.cs`

## git push

上面的所有命令都是在自己的电脑上玩，而git最重要的部分就是和多人进行协助和配合，所以我们最终的增删改查需要同步到远程服务器中供其他人使用（注意这里提交，需要输入账号密码），it's so easy!

`git push `


## git remote 

刚刚学习了git push 命令,因为我们的项目是从git clone 来的，所以我们的项目的 remote直接关联到了远程的git服务器.
我们可以通过如下git remote 查看当前项目的远程地址

`git remote -v`

接着我们可以添加远程服务器地址

`git remote add [serverName] [url]`

如果我们更换了服务器地址,那么我们可以对无用的服务器地址可以进行删除操作

`git remote rm [serverName]`

显示serverName的详细地址

`git remote show [serverName]`
