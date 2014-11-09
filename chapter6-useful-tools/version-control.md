# 版本控制

文本编辑器很好地解决了码字的问题，于是另一个问题来了——在一个项目的开发过程中需要和很多人一起合作，而且随着时间的推进代码会产生多个不同的版本。比较直观的想法是用文件名重命名的方式管理，如`file0.c, file1.c...`, 稍微好点的会用`file-2014-10-05.c...` 这种版本管理方式对于稍微有点规模的项目来说就显得有点太naive了，再说自己改着也蛋疼乳酸是不是？聪明的程序员早已为你想好了解决办法——Version Control(版本控制)! 专业的事情就应该交给专业的工具去解决。于是另一个问题又来了——**版本控制工具那么多，到底哪家强？蓝翔貌似没有版本控制工具啊...** 随便一搜就能发现以下几种：

1. [Git](http://zh.wikipedia.org/wiki/Git)
2. [Subversion](http://zh.wikipedia.org/wiki/Subversion)
3. [Mercurial](http://zh.wikipedia.org/wiki/Mercurial)

整体来讲，版本控制可以分为两种，分布式的和非分布式的 ←\_← 非分布式的可以理解为集中式的，也就是说在使用时必须有一个集中式的服务器。就像军训训练时出队必须向排长报告，这个排长就相当于集中式版本控制工具中的服务器啦。你想啊，你做什么都需要向排长报告，自然是相当不爽对不对π\_π 其中的代表就是Subversion啦。

如果这个版本控制的服务器离你十万八千里，而这时恰好某位熊孩纸有事没事拔掉你的网线，摁下路由器的开关——总之就是不能让你不能愉快的连接国外的服务器就是了，那么这个时候团队合作自然是无法愉快地进行下去了。既然和集中式版本控制做不成朋友，那就让我们和土豪分布式版本控制工具做朋友吧！弃Subversion，保平安～

就连Subversion本身的开发也已于2014年愚人节转向使用git，噗哈哈哈，投票最后竟然通过了... [[svn1]](#ref-quit-sub) [[svn2]](#git-svn-diff) [[svn3]](#svn-april-fool)

## 分布式版本控制工具 - git

分布式的好处在于，它可以不像集中式版本控制工具那样依赖中心服务器，开发完全可以在本地进行，不依赖网络。其中的代表就是[Git](http://zh.wikipedia.org/wiki/Git)啦。Git是 Linus Torvalds 继 Linux 之后给全人类带来的另一大神器，骚年颤抖吧！先放一张git在分支和合并方面的大杀器特性给大家醒醒脑，强大伐？

![Git-branch](../images/git-branch-1.png)


### 实用教程

1. [git - 简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)，目前见过的最简git指南，原来的英文版被翻译成了各种其他语言，漫画超友爱 ≖‿≖✧
2. [Git 简要教程](https://gist.github.com/bigeagle/3953973)，b哥整理的教程，简洁实用。
3. [Git分支管理策略](http://www.ruanyifeng.com/blog/2012/07/git.html)，阮一峰提供的针对Git分支管理策略。
4. [Git教程 - 廖雪峰](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000) - 浅显易懂的git中文教程
5. [Git Magic](http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/zh_cn/)，挺适合入门的教程，文字超友爱 ≖‿≖✧
6. [Pro Git](http://git-scm.com/book)，官方教程，非常全面，简单入门的话先看前几章就够用了。


## Notes

1. <a name="ref-quit-sub">[svn1]</a> [为什么我们要放弃Subversion](http://www.infoq.com/cn/articles/thoughtworks-practice-partiv)
2. <a name="git-svn-diff">[svn2]</a> [GIT和SVN之间的五个基本区别 | 外刊IT评论](http://www.vaikan.com/5-fundamental-differences-between-git-svn/)
3. <a name="svn-april-fool">[svn3]</a> [[INFRA-7524] April Fools: migrate Apache Subversion project over to the git repo - ASF JIRA](https://issues.apache.org/jira/browse/INFRA-7524)
