# git 学习

## git 命令

1. git init 
2. git clone 
3. git remote
4. git status


## git clone 

第一次听到git就是在github兴起的时候，因为有很多优秀的开源项目都放在github上，要想提升自己的开发水准,一定要多看别人的优秀项目.那么首先我们在看项目的的时候,需要将项目下载下来,所以就要下载项目源码，第一个git命令就来了，来看一下如何下载源码吧。

`   git clone https://github.com/vuejs/vue.git`

## git add --<文件名>

当你有一天看到别人的源码有问题或者需要添加某种功能的时候，你会提交代码，那么你就会用到git add 命令，它的作用的将你修改的文件暂存到本地，如下例子

`   git add xxx.cs `

如果你变更的代码很多可以一次性暂存全部文件

`   git add .`

## git checkout --<文件名> 

时光回溯,如果你想放弃自己修改的内容,在windows 系统中我们一般用ctrl+z ，而在git中我们可以用git checkout xxx.cs命令来进行内存撤销

`   git checkout xxx.cs`

## git commit -m '内容'

前面两个命令，都是临时性的保存文件，如果我们要永久保存的话，我们需要进行 commit ，commit后就会将我们改动的内容保存到本地的git库中了

`   git commit -m 'hello git'`

## git status 

通过上面的几个命令，我们可以将修改的内容进行保存了，此时我们如果想知道项目文件的状态，那么就是用status,如果对git熟悉了后，可以带-s参数，git会提供简单的信息


`   git status -s `
