# 第六章-编程方法论杂谈

不管是在学习计算机编程还是其他领域的知识，只学到课堂上的那点东西是远远不够的，现代社会的发展对人的终生学习提出了新的挑战，在快速发展的IT业，不会终身学习也就相当于是退休了。下文就我在计算机领域所接触到的一些好的方法和工具给大家集中推荐一下。方法么，在很多领域都是相通的，因此以下的这些文字说不定就对你有用咧～

## 编程工具链

工欲善其事，必先利其器。以下就编程工具链推荐一些效率型工具。

### 文本编辑器

在节[不会Coding如何破？](../chapter3-advanced-programming-part1/README.html#sec-coding)中提到：「一旦算法（伪代码）描述齐备，程序编写不过是打字校对的工作。」咱们平时学习工作都非常讲究效率，那么「打字校对」的工作是不是也可以也有一些比较好的办法来提高效率呢？答案是肯定的！一些聪明的程序员早已想好了各种办法来提高Coding的效率，其中之一便是选择一款适合自己的高效Text Editor（用来输入程序代码的玩意儿，称为文本编辑器）。

Windows下大家最常见的恐怕就是记事本程序咯，够小巧，但我想应该没几个人愿意一直用这玩意儿吧？输几行代码进去它似乎什么反应也没有，代码高亮也没有。Linux 下最普通的便是 nano 了。不过比起下面即将出场的两位大神恐怕他们都得往一边站，OK,该轮到Vim和Emacs出场了。

* Vim-the god of editors
* Emacs-the god’s editor

#### Vim-Vi IMproved

Vim是从vi发展出来的一个文本编辑器。代码补全、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。开始学习的时候可能会进展缓慢，但是一旦掌握一些基本操作之后，能大幅度提高编辑效率。左耳朵耗子写的[Vim系列教程](http://coolshell.cn/tag/vim)十分不错。其中最适合入门的非[简明 Vim 练级攻略](http://coolshell.cn/articles/5426.html)莫属。下面放一张[给程序员的VIM速查卡](http://coolshell.cn/articles/5479.html#more-5479).

![Vim-cheat-sheet](../images/vim_cheat_sheet_for_programmers_print.png)

最后再力荐下BeiYuu的[Git时代的VIM不完全使用教程](http://beiyuu.com/git-vim-tutorial/)，使用Vundle管理Vim插件太惬意了。

#### Emacs-Editor MACroS

Emacs即Editor MACroS（宏编辑器），是一种文本编辑器，在程序员和其他以技术工作为主的计算机用户中广受欢迎。由于我不是Emacs用户，相关入门教程啥的还请Emacs党补充...

#### Sublime Text

除了以上两款神器，最近几年还冒出了个新一代神器——[Sublime Text: The text editor you'll fall in love with](http://www.sublimetext.com/)。简洁美观，上手特别容易，第三方插件也是异常丰富！觉得 Vim 和 Emacs 学习曲线太抖的可以尝试下这款性感的编辑器，不过得小声地说一句这款编辑器是商业软件，虽然可以免费使用。

和平时大多数人用 WPS, Word 和 LaTeX 写文档一样，用的熟练的人很快就能完成一份精美的文档，而对于不熟练的人来说就只能面对屏幕望洋兴叹喽，学习新事物是需要成本的，你现在的每一滴汗水都是在为你自己的将来投资。

### 版本控制

文本编辑器很好地解决了码字的问题，于是另一个问题来了——在一个项目的开发过程中需要和很多人一起合作，而且随着时间的推进代码会产生多个不同的版本。比较直观的想法是用文件名重命名的方式管理，如`file0.c, file1.c...`, 稍微好点的会用`file-2014-10-05.c...` 这种版本管理方式对于稍微有点规模的项目来说就显得有点太naive了，再说自己改着也蛋疼乳酸是不是？聪明的程序员早已为你想好了解决办法——Version Control(版本控制)! 专业的事情就应该交给专业的工具去解决。于是另一个问题又来了——**版本控制工具那么多，到底哪家强？蓝翔貌似没有版本控制工具啊...** 随便一搜就能发现以下几种：

1. [Git](http://zh.wikipedia.org/wiki/Git)
2. [Subversion](http://zh.wikipedia.org/wiki/Subversion)
3. [Mercurial](http://zh.wikipedia.org/wiki/Mercurial)

整体来讲，版本控制可以分为两种，分布式的和非分布式的 ←\_← 非分布式的可以理解为集中式的，也就是说在使用时必须有一个集中式的服务器。就像军训训练时出队必须向排长报告，这个排长就相当于集中式版本控制工具中的服务器啦。你想啊，你做什么都需要向排长报告，自然是相当不爽对不对π\_π 其中的代表就是Subversion啦。

如果这个版本控制的服务器离你十万八千里，而这时恰好某位熊孩纸有事没事拔掉你的网线，摁下路由器的开关——总之就是不能让你不能愉快的连接国外的服务器就是了，那么这个时候团队合作自然是无法愉快地进行下去了。既然和集中式版本控制做不成朋友，那就让我们和土豪分布式版本控制工具做朋友吧！弃Subversion，保平安～ 就连Subversion本身的开发也已于2014年愚人节转向使用git，噗哈哈哈，投票最后竟然通过了... [[svn1]](#ref-quit-sub) [[svn2]](#git-svn-diff) [[svn3]](#svn-april-fool)

#### 分布式版本控制工具 - git

分布式的好处在于，它可以不像集中式版本控制工具那样依赖中心服务器，开发完全可以在本地进行，不依赖网络。其中的代表就是[Git](http://zh.wikipedia.org/wiki/Git)啦。Git是 Linus Torvalds 继 Linux 之后给全人类带来的另一大神器，骚年颤抖吧！先放一张git在分支和合并方面的大杀器特性给大家醒醒脑，强大伐？

![Git-branch](../images/git-branch-1.png)

下面介绍一些Git方面的入门资料。

1. [git - 简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)，目前见过的最简git指南，原来的英文版被翻译成了各种其他语言，漫画超友爱 ≖‿≖✧
2. [Git 简要教程](https://gist.github.com/bigeagle/3953973)，b哥整理的教程，简洁实用。
3. [Git分支管理策略](http://www.ruanyifeng.com/blog/2012/07/git.html)，阮一峰提供的针对Git分支管理策略。
4. [Git Magic](http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/zh_cn/)，挺适合入门的教程，文字超友爱 ≖‿≖✧
5. [Pro Git](http://git-scm.com/book)，官方教程，非常全面，简单入门的话先看前几章就够用了。

## 提升效率

### 如何找到好书

这个问题十分关键，也是我们最应该分享给读者的。**授之以鱼，不如授之以渔。**全世界每天都在出版各种不同的书，我们不可能有那么多时间一本一本去挑。一般来说，经典书籍肯定是要经得起大家的检验的。

在国内出版电子计算机方面教材比较多的出版社有人民邮电出版社、电子工业出版社、清华大学出版社以及机械工业出版社，这四家出版社出好书的可能性相对会大一些，但并不意味着出的都是好书。国外的Addison Wesley, Microsoft Press, McGraw Hill, Pearson & O'Reilly也是尽出猛书的地方，像Addison Wesley, Pearson, McGraw Hill这三家出的其它比如数理电子类教材经典的也比较多，图书馆到处都能看到这三家出版社的书。

以上是从大的范围去挑，书是人写的，书好不好在很大程度上是由编者水平决定的，所以说要去找某领域比较好的书籍可以先找找这个领域有哪些领军人物，再去看看TA都写了什么书。

如今的网络十分发达，信息的公开程度也越来越高，像国内的[豆瓣](http://www.douban.com)在书籍、电影评论这一块就做的非常不错，有很多很多圈子和小组供你查看，如果是比较好的书的话上边一般都会有较多评价，我们可以根据上边的评分以及评论进行抉择。国内买书推荐去[卓越亚马逊](http://www.amazon.cn)和[当当](http://www.dangdang.com)，但是这两家网店上的书评就不咋滴了，用户参与评论的积极性不够高。国外的网站推荐到[Amazon](http://www.amazon.com)看看，记住不要把国外的这个网站和国内的卓越亚马逊混一块了，Amazon上的书评很有参考价值。再者就是一些论坛了，不过国内的论坛总体而言显得很乱，国内网民的参与积极性也不像欧美国家那么高，很多回复只是灌水而已，毫无价值可言。国内的[CSDN](http://www.csdn.net)算是IT方面比较齐全的网站了，但是现在里边特别乱，提问题后得到比较满意的答复的可能性较小。在资料整合这一块个人认为[大家网论坛](http://club.topsage.com)做的不错，社区不少资料就是从它上边弄下来的，不过自己要注意资料的取舍。

最后还是想提的就是建议大家学会使用Google & Wikipedia, 这两个东西组合在一起能解决你绝大部分问题，更是你成长的催化剂。

有关Google的使用方法在它首页的帮助里边有，找时间看看。

### 高效使用搜索引擎

## 好习惯

### 编码风格

代码风格好不好就像字写得好不好看一样，如果一个公司招聘秘书，肯定不要字写得难看的，同理，代码风格糟糕的程序员肯定也是不称职的。虽然编译器不会挑剔难看的代码，照样能编译通过，但是和你一个Team的其他程序员肯定受不了，你自己也受不了，写完代码几天之后再来看，自己都不知道自己写的是什么。Thus, programs must be written for people to read, and only incidentally for machines to execute. 代码主要是为了写给人看的，而不是写给机器看的，只是顺便也能用机器执行而已，如果是为了写给机器看那直接写机器指令就好了，没必要用高级语言了。代码和语言文字一样是为了表达思想、记载信息，所以一定要写得清楚整洁才能有效地表达。正因为如此，在一个软件项目中，代码风格一般都用文档规定死了，所有参与项目的人不管他自己原来是什么风格，都要遵守统一的风格。[2]在编程初期就要养成好的习惯！！！

# 学习习惯与工具
* 书籍：简单经典的入门或者概论类书籍，可以在豆瓣或者Amazon美国官网上对比
* 经典论文：引用次数最多或是被收藏次数最多，使用Google Scholor即可
* 搜索引擎前几十页：推荐Google
* 行业专家观点或是博客：可使用RSS订阅
* 与同行专业人士交流：参与社区交流——研讨会，网络论坛，邮件列表
*



[2] 本段大部分内容引自《Linux C编程一站式学习》-http://learn.akae.cn/media/ch09.html 如与GFDL许可证相冲突，请作者及时指出。

### 编程工具的使用

* * * * *

待整合完善

前边说了那么多编程的东西，那么怎么把自己的想法变为最终的结果呢？——当然是选择合适的编译器（或者类似的东西）啦，首推GCC\#，关于编译器在这就不多介绍了，前边已经做过初步解释，初学者无需在此浪费过多时间，知道它能把你的代码翻译为计算机可执行的文件就OK了。下边针对C/C++做些介绍，其它语言类似。

就国内的高校C语言教学来说，Windows下的VC6.0使用率还是比较广的，估计大部分都是用的盗版汉化软件，我大一一开始学的时候老师上课演示也是用VC6.0示范的，不得不在这里小小的抗议一下，初学编程完全无需VC6.0(在Win7下兼容性很成问题)甚至Visual Studio这样的庞然大物，光建工程配置文件就能打击一大批新手的自信心，而且莫名其妙的错误是经常会有的！对于初学者，个人觉得Linux + Terminal就非常不错，能配合《Linux C一站式编程》就更完美了。

如果你喜欢IDE，那也没关系，免费开源的[<http://zh.wikipedia.org/wiki/Code>::Blocks Code::Blocks]，自由小巧的[Dev-C++](http://zh.wikipedia.org/wiki/Dev-C%2B%2B)也不错，如果你平时使用多种语言开发，开源的Eclipse当仁不让。当然咯，如果你钟情于Windows，Visual Studio则比较适合你，初学时可以用免费的Express版，也可以使用微软授权给高校学生授权的Professional版本。

另外值得一提的就是软件调试，这本是一块很大的话题，《Linux C一站式编程》中有关gdb的使用已经很详细了，有兴趣的去看看，其它IDE或多或少也有类似的排错功能，使用方法见各软件帮助文档或网络上的教程。

除了IDE这种开发方式，你也可以使用前边提到过的Text Editor配合编译器使用，配置好的话熟练后非常方便，效率也较高。更多的介绍请参考Wikipedia或者社区wiki之[工具篇](如何用C/C++做工程 "wikilink")。

### Notes

1. <a name="ref-quit-sub">[svn1]</a> [为什么我们要放弃Subversion](http://www.infoq.com/cn/articles/thoughtworks-practice-partiv)
2. <a name="git-svn-diff">[svn2]</a> [GIT和SVN之间的五个基本区别 | 外刊IT评论](http://www.vaikan.com/5-fundamental-differences-between-git-svn/)
3. <a name="svn-april-fool">[svn3]</a> [[INFRA-7524] April Fools: migrate Apache Subversion project over to the git repo - ASF JIRA](https://issues.apache.org/jira/browse/INFRA-7524)
