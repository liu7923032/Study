# git 高级使用


git 强大的地方就在于多人协同功能，在之前的学习的git基本命令[git 基础](git-base.md),在此章我们来学习一下git协同开发功能。在介绍协同开发之前，我们先了解一下git的原理，在前一节中，我们学会了copy代码，修改代码，最后提交代码。注意一下，我们提交代码提交的实际是git服务器上面的master分支的源码中。

下面是今天要学习的git相关命令
1. git branch : 查看所有分支，其中前面有星号的是当前所在分支，下方即为master分支。
2. git branch -v : 查看所有分支和该分支上最后的一次提交。
3. git branch <分支名> 创建分支
4. git checkout <分支名> 切换分支
5. git checkout -b <分支名> 创建分支并切换分支
6. git merge <分支名> 合并分支
7. git branch [serverName] -d <分支名> 删除分支
7. git branch --merged : 查看已经合入当前分支的所有分支。
8. git branch --no-merged : 查看未被合入分支。


## 分支创建和切换

### git branch 

在学习命令之前，我们先想象一种情况，假如张三变更了xx.cs文件，并向git服务器mater提交了代码，而后李四也在本地修改了xx.cs文件，并项目服务器提交代码，那服务器到底是认同张三的代码还是李四的代码？

***
在git中出现了分支(**branch**)的概念，它的目的就是主要解决在团队开发过程中出现代码文件冲突的问题的。
***

当项目涉及到多人开发的时候，我们在从服务器拉取代码后，不要在当前分支中修改代码，一定要创建一个分支，然后将分支合并到master分支上面。

`git branch` 命令可以查看当前项目所在分支。

`git branch dev` 命令创建了名字叫**dev** 的分支，注意此时我们在操作时，还是在master分支上对项目调整

### git checkout <分支名>

在分支创建后，需要我们将仓库切换到新的分支上，我们才可以对项目进行操作。

`git checkout dev` 命令切换到dev，此时我们就可以在**dev**分支上修改我们的代码了。（修改文件后，需要commit，这样我们修改的代码才真正提交到分支**dev**中）
可以通过`git log --oneline`命令才查看head是否指向dev分支。

### git checkout -b <分支名>

上面的命令是先创建分支，我们可以使用命令`git checkout -b dev_bug` 直接进行创建并切换到**dev_bug**分支，最后我们可以使用`git commit -m ''`命令来对变更的信息就行提交。


## 分支的合并

在上面的讲解git 分支的过程中，我们创建了两个分支**dev**和**dev_bug**，在两个分支中，我们对项目操作完了，那么我们现在想将代码都提交到mater分支上，怎么处理呢？

### git merge 

1. 首先使用 `git checkout master` 命令将工作仓库切换到mater分支上面
2. 接着使用 `git merge dev` 命令对**dev**分支进行合并
3. 最后使用 `git merge dev_bug` 命令对**dev_bug**分支进行合并

## 分支的删除

### git branch [serverName] -d <分支名>

随着项目越来越大，改动也越来越多，我们有时随手建立的分支可能会越积越多，所以我们需要在确认不会使用的的分支进行删除。

```
git branch -d dev
git branch -d dev_bug
```
    
如果要删除远程服务器地址的分支，需要使用如下命令

```
git branch origin -d devs
```

## 冲突解决

如果在两个分支中都对同个文件做了不同的修改，在将分支合并到master分支上的时候，会产生冲突。

我们可以通过IDE来找到冲突项，最后我们删除提示的冲突异常，最后在mater分支中进行 **commit**操作和**push**操作，将代码提交到远程服务器中。
