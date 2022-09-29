# 初识git（一）

> 对于程序员来说，git是日常工作中必备技能，但是其中很多人对git一知半解，因为工作基本场景就那些，而且大部分场景下，我们只用其中一些git常用命令，例如：`git pull` 、`git fetch`、`git merge`、`git add`、`git commit`、`git push`、`git reset`、`git revert`、`git stash`、`git pop` ......。
但这样其实很不好，简单场景还ok，遇到一些复杂场景的时候，你对git不足够理解的话，很难去处理它，有时候盲目处理也会给个人、团队造成不必要额度损失。
自己其实就是属于似懂非懂的状态的那类人，所以也想系统学习一下git，同时写一些文章去梳理思路、也倒逼自己输出。

## git简介
git是林纳斯创作的分布式版本控制软件，最初是用来更好的管理Linux核心开发而设计的，后来成为了一个流行的版本控制工具，使用成为了现在程序员开发的必备能力。

特点：
- 分布式（和集中式相对）
- 速度快
- 强大的版本控制能力
- C语言开发 性能极高


.git库目录：
- hooks 存放钩子
- logs 存放日志
- refs 存放指向各个分支的指标(HEAD)文件
- objects 存放git对象
- config 存放各种设置文档
- HEAD 指向当前所在分支的指标文件，一般指向refs下的某文件

数据结构：
- 可变的版本信息
- 不变的对象数据库

常用命令:
- HEAD是一个指针
- git reset --hard  HEAD^/HEAD^^/HEAD~100/commit id
  版本回退，HEAD指的是当前版本，上面的操作分别对应回退上一个版本、上上版本、上上上版本、之前100版本、指定commit id的版本号。
  如果不小心reset错了，如果命令行没有关闭就可以reset回去.
  回退的低层逻辑其实就是把HEAD指向改变了。
- git commit
 快照
- git reflog
  显示的是一个 HEAD 指向发生改变的时间列表,记录你的每个快照，会定期清理的。
- git config [--global]
- git diff
- git branch -M xxxx 修改分支名字为xxxx
- git push -u 第一次推送的时候加上
- git cherry-pick 将一个commit copy到现在的分支上，更改一样，但是会产生一个新的commit
- git stash  未commit的全部都存起来
- git rebase
- git tag

三个区域
- 工作区
- 暂存区
- 分支上


![alt](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d8/Git_operations.svg/1253px-Git_operations.svg.png)

今日summery:
    HEAD其实就是一个指针，指向当前分支的指针，间接指向了分支最新commitID；
    可以checkout 到一个commitid，这样的话就成为了detached HEAD；
    ⭕️就是现在的HEAD的指向


引用：
【1】 [维基百科git](https://zh.m.wikipedia.org/zh-hans/Git)
【2】 [廖雪峰git教程](https://www.liaoxuefeng.com/wiki/896043488029600/896202815778784)
 【3】[朱双印git教程](https://www.zsythink.net/archives/3412)