# 1. 起步
## 1.1 关于版本控制
版本控制是一种记录一个或若干个文件内容变化，以便将来查阅特定版本修订情况的系统。实际上可以对任何类型的文件进行版本控制。

在分布式控制系统中，客户端把代码仓库完成的镜像下来，包括完整的历史记录，这样任何一处协同工作用的服务器发生故障，事后都可以用任何一个镜像出来的本地仓库恢复。每一次的克隆操作，实际上都是一次对代码仓库的完整备份。

## 1.2 Git是什么
**直接记录快照，而非差异比较**
Git中每次提交更新后保存项目状态时，基本上就会对当时的全部文件创建一个快照并保存这个快照的索引。
Git对待数据更像是一个快照流。

**近乎所有操作都是本地执行**
在Git中的绝大多数操作都只需要访问本地文件和资源，一般不需要来自网络上其它计算机的信息。

**Git保证完整性**
Git中所有的数据在存储前都计算校验和，然后以校验和来引用。这意味着不可能在Git不知情时更改任何文件内容或目录内容。

**Git一般只添加数据**
很难使用Git从数据库中删除数据，Git 几乎不会执行任何可能导致文件不可恢复的操作。

**三种状态**
- 已提交（committed）
  表示数据已经安全的保存在本地数据库中。
- 已修改（modified）
  表示修改了文件，但还没保存到数据库中。
- 已暂存（staged）
  表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。

工作区是对项目的某个版本独立提取出来的内容。
暂存区是一个文件，保存了下次将要提交的文件列表信息。
Git仓库是Git用来保存项目的元数据和对象数据库的地方。

Git工作流程：
1. 在工作区中修改文件
2. 将想要下次提交的更改选择性的暂存，这样只会将更改的部分添加到暂存区
3. 提交更新，找到暂存区的文件，将快照永久性存储到Git目录

## 1.3 安装Git
[Git Download](https://git-scm.com/downloads)

检查git版本

```bash
git --version
```

## 1.4 初次运行Git前的配置
查看所有配置文件

```bash
git config --list --show-origin
```

**用户信息**

设置用户名和邮件地址

```bash
git config --global user.name "xxx"
git config --global user.email xxxx@xxx.com
```

# 2. Git基础
## 2.1 获取Git仓库
**在已存在的目录中初始化仓库**
如果你有一个尚未进行版本控制的项目目录，想用Git来控制它，首先进入该项目目录中，然后执行`git init`，该命令创建一个名为`.git`的子目录，这个目录含有初始化的Git仓库中所有的必须文件，但是目前仅仅是一个初始化操作，项目里的文件还没有被跟踪。通过`git add`命令来指定需要的文件来进行跟踪，然后执行`git commit`。

**克隆现有仓库**
比如你想拷贝一个开源项目，使用`git clone <url>`命令。

```bash
git clone https://github.com/6haojian/To-Be-Top-Programmer.git
```

这会在当前目录下创建"To-Be-Top-Programmer"目录，并在这个目录下初始化一个`.git`文件夹，从远程仓库拉取所有数据放入`.git`文件夹，然后从中读取最新版本的文件的拷贝。

## 2.2 记录每次更新到仓库
**检查当前文件状态**

```bash
git status
```

**跟踪新文件**

```bash
git add filename
```

**暂存已修改的文件**
`git add`命令是个多功能命令，将这个命令理解为“精确的将内容添加到下一次提交中”而不是“将一个文件添加到项目中”。

```bash
git add filename
```

运行了 `git add` 之后又作了修订的文件，需要重新运行 `git add` 把最新版本重新暂存起来。

**状态简览**

```bash
git status -s
```

**忽略文件**
一些不需要的文件无需纳入Git管理

文件`.gitignore`，使用标准的glob模式匹配（shell简化的正则表达式）

```
# 忽略所有的.a文件
*.a

# 但跟踪所有的lib.a，即使前面忽略了.a文件
!lib.a

# 只忽略当前目录下的TODO文件，而不忽略 subdir/TODO
/TODO

# 忽略任何目录下名为build的文件夹
build/

# 忽略doc/notes.txt，但不忽略doc/server/arch.txt
doc/*.txt

# 忽略doc/ 目录及其所有子目录下的.pdf文件
doc/**/*.pdf
```

**查看已暂存和未暂存的修改**
- 当前做的哪些更新尚未暂存
- 哪些更新已暂存并准备下次提交

```bash
git diff
```

此命令比较工作目录中当前文件和暂存区域快照之间的差异，也就是修改之后还没有暂存起来的变化的内容。

```bash
git diff --staged
```

此命令比较已暂存文件与最后一次提交的文件差异。

**提交更新**
每次提交前，先用`git status`看下，需要的文件是不是已暂存，然后再执行`git commit`

```bash
git commit -m "first commit"
```

每次的提交都是对项目做一次快照，以后可以回到这个状态或进行比较。

**移除文件**

```bash
git rm
```

**移动文件**
底层实际是先删除文件再重新添加

```bash
git mv file1 file2
```

## 2.3 查看提交历史
```bash
git log
```

`git log`按时间先后顺序列出所有提交，最近的更新排在最上面。

```bash
git log --stat
```

`--stat`选项在每次提交的下面列出所有被修改过的文件、有多少文件被修改了以及被修改的文件的哪些行被移除或是添加了。

```bash
git log --pretty=oneline
```

将每个提交放在一行显示，在浏览大量的提交时非常有用。

## 2.4 撤销操作

**撤销操作**
提交完后发现遗漏了几个文件没有添加，或者提交信息写错了，`--amend`选项重新提交（相当于覆盖上一次提交）
```bash
git commit --amend
```

**取消暂存的文件**

```bash
git reset HEAD filename
```

**撤销对文件的修改**
```bash
git checkout -- filename
```

## 2.5 远程仓库的使用
**查看远程仓库**
```bash
git remote -v
```

`git clone`自动添加远程仓库
`git remote add <shortname> <url>`手动添加同时指定简写

```bash
git remote add 
```

**从远程仓库中抓取与拉取**
```bash
git fetch <remote>
```

这个命令会访问远程仓库，从中拉取所有你还没有的数据。执行完后，将拥有那个远程仓库中所有分支的引用，可以随时合并或查看。

如果使用`git clone`克隆了一个仓库，命令会自动将其添加为远程仓库并默认以“origin”为简写。`git fetch`命令只会将数据下载到本地仓库，它不会自动合并或修改你当前的工作。当准备好时，必须手动将其合并入你的工作。

默认情况下，git clone 命令会自动设置本地 master 分支跟踪克隆的远程仓库的 master 分支。

**推送到远程仓库**
```bash
git push origin master
```

## 2.6 打标签
Git可以给仓库历史中的某一个提交打上标签，以示重要，比如标记发布节点（v1.0,v2.0等）

**列出标签**
    git tag

**创建标签**
- 轻量标签
  它只是某个特定提交的引用
- 注释标签
  Git仓库中的一个完整引用，它们是可以被校验的，其中包含了打标签者的名字、电子邮件、日期等

**附注标签**
    git tag -a v1.0 -m "released"

`git show v1.0`查看标签信息

**轻量标签**
    git tag v1.0-lw

默认`git push`不会传送标签到远程仓库服务器，在创建完标签后必须显式推送标签到共享服务器。
    git push origin v1.0

**删除标签**
    git tag -d v1.0-lw
    git push origin --delete <tagname>

远程仓库中的标签必须显式删除。

# 3. Git分支
使用分支意味着你可以把你的工作从开发主线上分离开来，以免影响开发主线。

**分支简介**
在进行提交操作时，Git保存的不是文件的变化或者差异，而是一系列不同时刻的**快照**。

在提交时，Git会保存一个提交对象，该提交对象包含一个指向暂存内容快照的指针。该对象还包含作者姓名和邮箱、提交时输入信息以及指向它的父对象的指针。首次提交产生的提交对象没有父对象，普通提交操作产生的提交对象有一个父对象，而由多个分支合并产生的提交对象有多个父对象。

假设现在有一个工作目录，里面包含了三个将要被暂存和提交的文件。暂存操作为每个文件计算checksum，然后把当前版本的文件快照保存到Git仓库中（Git将它们当做blob对象），最终将checksum加入到暂存区域等待提交。
现在Git仓库中有5个对象：三个blob对象（保存文件快照）、一个树对象（记录目录结构和blob对象树索引）以及一个提交对象（包含指向前述对象的指针和所有提交信息）

![首次提交及其树结构](https://git-scm.com/book/en/v2/images/commit-and-tree.png "首次提交对象及其树结构")


做些修改后再提交，那么这次产生的提交对象会包含一个指向上次提交对象的指针。

![提交对象及其父对象](https://git-scm.com/book/en/v2/images/commits-and-parents.png "提交对象及其父对象")

Git分支本质上仅仅是指向提交对象的可变指针。Git默认分支名字是master，master分支会在每次提交时自动向前移动。

> Git master分支并不是一个特殊分支，git init命令默认创建它，并且大多数人懒得改动它。


![分支及其提交历史](https://git-scm.com/book/en/v2/images/branch-and-history.png "分支及其提交历史")

**分支创建**
    git branch testing

这会在当前分支所在的提交上创建一个指针。

Git通过名为**HEAD**的特殊指针，指向当前所在的本地分支（HEAD想象为当前分支的别名）。

`git branch`命令仅仅创建一个新分支，并不会自动切换到新分支中去。

**切换分支**
    git checkout testing

这条命令做两件事，一是使HEAD指回master分支，二是将工作目录恢复成master分支所指向的快照内容。

> 在切换分支时，一定要注意你工作目录里的文件会被改变。 如果是切换到一个较旧的分支，你的工作目录会恢复到该分支最后一次提交时的样子。

通常我们会在创建一个新分支后立即切换过去，这可以用 `git checkout -b <newbranchname>` 一条命令搞定。

## 3.1 分支的创建和合并
**新建分支**
    git checkout -b iss53

**分支合并**
将分支合并入master分支
    git checkout master
    git merge iss53

其余分支做了修改，合并到master后，拉取所做的修改
    git merge master


# 远程分支
`git clone`自动将其命名为origin，拉取它的所有数据，创建一个指向它的master分支的指针，并且在本地将其命名为origin/master。Git也会给你一个与origin的master分支在指向同一个地方的本地master分支。

![克隆之后的服务器与本地仓库](https://git-scm.com/book/en/v2/images/remote-branches-1.png "克隆之后的服务器与本地仓库")

如果要与给定的远程仓库同步数据，运行`git fetch <remote>`命令，从中抓取本地没有的数据，并且更新本地数据库

**推送**
    git push


**拉取**
    git fetch

当 git fetch 命令从服务器上抓取本地没有的数据时，它并不会修改工作目录中的内容。 它只会获取数据然后让你自己合并。



# Reference
Git D
Git Doc[^1]

[^1]: https://Git-scm.com/book/en/v2
