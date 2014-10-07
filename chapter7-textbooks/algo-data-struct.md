# 数据结构与算法类

## 教材及MOOCs

### The Art of Computer Programming

Author: Donald E. Knuth

中文书名：计算机程序设计艺术，简称 **TAOCP** ，号称是经典中的经典，每一个想要掌握算法精髓的人都必须看的书，算法书中的圣经。**镇楼专用，新手请勿当作入门书去读，会吐血的。**

说到这本书就忍不住想多介绍下高爷爷的生平。

1938年初，高德纳出生于美国威斯康辛州。毕业于加州理工学院的他，目前是美国著名的计算机科学家，并且是斯坦福大学计算机系荣誉退休教授。高德纳的英文全名为：Donald Ervin Knuth。他的中文名是1977年到中国来之前，姚储枫为他取的。Knuth从此用高德纳作为其在Unicode世界的名字。

TAOCP这套关于算法分析的多卷论著已经长期被公认为经典计算机科学的定义性描述。迄今已出版的完整的三卷(第四卷已有部分出版)已经组成了程序设计理论和实践的惟一的珍贵资源，无数读者都赞扬Knuth的著作对个人的深远影响，科学家们为他的分析的美丽和优雅所惊叹，而从事实践的程序员已经成功地将他的「菜谱式」的解应用到日常问题上，所有人都由于Knuth在书中表现出的博学、清晰、精确和高度幽默而对他无比敬仰。

他因这些成就以及大量富于创造力和具有深远影响的著作（19部书，160篇论文）而誉满全球。这么说吧，目前你所能听说过或者还活着的那些计算机软件大牛，没有哪个不直接或间接的受过Knuth的教导。他强悍的程度只用一件小事就可以说明，在撰写这套《计算机程序设计艺术》的过程中，由于感到原有排版系统的不足，他特地重新制作了一套新的计算机排版系统，这套称为TEX的东西目前已经是出版界的标准系统。

1968年，刚刚进入Stanford的高德纳开始准备出版经典巨著《计算机程序设计艺术》，据说当时他一口气写了3000页，自此他计划写七卷（目前已经完成四卷）。这七卷分别为：基础算法、半数值算法、排序与查找、组合算法、造句算法、与上下文无关语言理论、编译器技术。1999年底，该书被美国科学家期刊列为20世纪最佳12部学术专著之一。

建议到豆瓣和Amazon上仔细看看评论或者看看印刷版，这一套书虽然很多人都极力推崇，但并不见得他们都看过，个人觉得中文翻译的看起来有点别扭，建议还是看英文原版的好了。**纸上得来终觉浅，绝知此事要躬行。**

### [Introduction to Algorithms - 算法导论 (豆瓣)](http://book.douban.com/subject/20432061/)

麻省理工学院计算机系的算法教材，已经成为世界范围内广泛使用的大学教材和专业人员的标准参考书。书很厚，适合当作工具书来使，看的时候可以结合MIT的课程讲义和视频。具体的讲义视频链接后再补充。

以上两本都是重量级的算法书，下面推荐一些轻量级的书。

### [Algorithms - 算法（第4版） (豆瓣)](http://book.douban.com/subject/19952400/)</dt>

Robert Sedgewick在算法方面写了不少好书，这本是他最近在算法书方面的大作，也是他所有算法书中读者评价最好的一本了，使用Java实现，之前有写过用C/C++实现的算法书。Coursera上将该书的内容分为了两个部分，[Algorithms, Part I | Coursera](https://www.coursera.org/course/algs4partI) 和 [Algorithms, Part II | Coursera](https://www.coursera.org/course/algs4partII) ，书中内容极其详细，中文版的没看过，但是英文原版的排版超级赞！

### [Problem Solving with Algorithms and Data Structures using Python](http://interactivepython.org/courselib/static/pythonds/index.html)

Python党的福利，作者免费在网上发布了电子版供大家阅读。用Python来写算法书的目前还不多，有其他好书推荐的可以发PR。

下面介绍一些用C/C++来写算法书的教材。

### [Algorithms in C++, Parts 1-4: Fundamentals, Data Structure, Sorting, Searching](http://www.amazon.com/Algorithms-Parts-1-4-Fundamentals-Structure/dp/0201350882/ref=sr_1_2?ie=UTF8&qid=1412603287&sr=8-2&keywords=Algorithms+Robert+Sedgewick)
### [算法I～IV（C++实现）――基础、数据结构、排序和搜索 (豆瓣)](http://book.douban.com/subject/1143801/)

### [Algorithms in C, Parts 1-4: Fundamentals, Data Structures, Sorting, Searching](http://www.amazon.com/Algorithms-Parts-1-4-Fundamentals-Structures/dp/0201314525/ref=sr_1_2?ie=UTF8&qid=1412603571&sr=8-2&keywords=Algorithms+in+C)
### [算法：C语言实现 (豆瓣)](http://book.douban.com/subject/4065258/)

C和C++的算法实现是 Robert Sedgewick较为早期的大作，虽然名气不及Java实现的那本，但如果看C或C++实现的算法书的话这两本还是不错的。Robert Sedgewick 在Princeton教了蛮久的书了。

## OJ


### OJ

* * * * *

Online Judge系统（简称OJ）是一个在线的判题系统。用户可以在线提交程序多种程序（如C、C++、Pascal）源代码，系统对源代码进行编译和执行，并通过预先设计的测试数据来检验程序源代码的正确性。[2]

OJ的题目大部分是关于算法的。题目的输入输出通常是命令行方式，而非图形界面。也就是说，要关注的不是平台的兼容性、文件的格式抑或窗口的布置这种无关紧要的细节，而是问题本身的逻辑实现。

一个用户提交的程序在Online Judge系统下执行时将受到比较严格的限制，包括运行时间限制，内存使用限制和安全限制等。用户程序执行的结果将被Online Judge系统捕捉并保存，然后再转交给一个裁判程序。该裁判程序或者比较用户程序的输出数据和标准输出样例的差别，或者检验用户程序的输出数据是否满足一定的逻辑条件。最后系统返回给用户一个状态：通过（Accepted, AC）、答案错误(Wrong Answer, WA)、超时(Time Limit Exceed, TLE)、超过输出限制（Output Limit Exceed, OLE)、超内存（Memory Limit Exceed, MLE）、运行时错误（Runtime Error, RE）、格式错误（Presentation Error, PE)、或是无法编译（Compile Error, CE），并返回程序使用的内存、运行时间等信息。

Online Judge系统最初使用于ACM-ICPC国际大学生程序设计竞赛和OI信息学奥林匹克竞赛中的自动判题和排名。现广泛应用于世界各地高校学生程序设计的训练、参赛队员的训练和选拔、各种程序设计竞赛以及数据结构和算法的学习和作业的自动提交判断中。

以下几个OJ都很不错，请随意进入，也可以自行搜索，国内很多学校的OJ正在热火朝天的建设中，有的甚至直接作为了考试用系统。

[西电ACM](http://acm.xidian.edu.cn/index) 搜搜百科上有一篇文章介绍得不错,[OJ](http://baike.soso.com/v708668.htm)

一个人孤单做题的滋味是很郁闷的，尤其是当你确实绞尽脑汁也搞不定的时候。幸好线上还是有很多同样在做题的朋友，他们通常会在论坛BBS或邮件列表之类的地方集中讨论解题心得，甚至有可用的答案。建议用OI (Olympiad in Informatics 信息学奥林匹克)[3]为关键字搜索。

哪里有代码示例可看？这个可以自己Google, 如果你已经能够做一些OJ的题了，那么可以考虑看一些开源软件的代码。http://sourceforge.net <http://github.com> <http://code.google.com> 上有很多开源软件，确定一个应用主题上去找就会有收获。不过说实话，从OJ到项目是有一定的跨越，所以要找到适合自己的项目来看是不容易的。可以尝试和他人合作做一些小型的项目[4]，边学边用，或者是找一些知名的但又比较小规模的项目，然后找他的早期版本的代码，会比较清晰，比如 vim1.0/2.0 lua1.0 apache1.0这种。

