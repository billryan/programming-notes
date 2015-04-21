# 编程笔记 By billryan

[![Build Status](https://travis-ci.org/billryan/algorithm-exercise.svg?branch=master)](https://travis-ci.org/billryan/algorithm-exercise)

弹指之间，从我开始接触编程至今已五年有余，从大一刚接触 C 语言到现在对计算机编程的一知半解，其中曲折坎坷一言难尽，这本在线笔记记录了我在学习计算机编程过程中的点点滴滴。

# About - 关于本文档

- 本笔记的在线托管仓库为 https://github.com/billryan/programming-notes 你可以在github中star本项目查看更新。
- 在线阅读网址为 http://prog-notes.yuanbin.me 在线阅读的网页通过gitbook后端生成，推送到github后会触发 gitbook 和 travis-ci 的编译，相应的编译输出下载链接提供Gitbook官网和七牛两种下载方式，七牛的链接中文显示比较好。
    1. Read on the [website](http://prog-notes.yuanbin.me). **力荐**
    2. EPUB. [Gitbook](https://www.gitbook.com/download/epub/book/yuanbin/programming-notes), [七牛](http://docs4bill.qiniudn.com/doc/programming_notes_billryan.epub) - Recommended for iPhone/iPad/MAC. 最适合离线查看，实测效果极好。
    3. 离线html. [七牛](http://docs4bill.qiniudn.com/doc/programming_notes_billryan_html.tar.gz) - 解压后即为整个网站的内容，用于本地查看，目前内容更新频繁，不推荐下载。
    4. PDF. [Gitbook](https://www.gitbook.com/download/pdf/book/yuanbin/programming-notes), [七牛- 适合打印版](http://docs4bill.qiniudn.com/doc/programming_notes_billryan_print.pdf) - Recommended for Desktop. 推荐下载七牛的版本。
    5. MOBI. [Gitbook](https://www.gitbook.com/download/mobi/book/yuanbin/programming-notes), [七牛](http://docs4bill.qiniudn.com/doc/programming_notes_billryan.mobi) - Recommended for Kindle. 未测试，感觉不适合在 Kindle 上看此类书籍，尽管 Kindle 的屏幕对眼睛很好...
- 全文大体上分为两大部分。
    1. 第一部分为 Part I Introduction to Programming, 是对计算机编程相对宏观的介绍，前身为「碧蓝右耳」07年发布的 [C/C++ FAQ](http://www.vcgood.com/BBS/forum_posts.asp?TID=1559)，我在此基础上做了大量的整合，以便适应如今蓬勃发展的计算机浪潮。
    2. 第二部分为 Part II Programming Notes, 是自己学习编程过程中的笔记，有语言特性，也有操作系统底层细节，还有一些专业软件等工具的使用小结。总之第二部分是比较杂啦，没有第一部分那么系统，偏向于个人笔记，摘抄的内容较多，所以第二部分不在下述公用创作协议授权范围之类，如果有你觉得不合适公开的内容，还请直接在相应页面下留言。
- 广而告之：本书的姊妹篇——[leetcode题解/算法笔记 | Data Structure and Algorithm](http://algorithm.yuanbin.me/) 也在火热更新中~

第一部分浅析了一些计算机编程背后蕴含的思想，同时提供了不少方法论层面上的技巧——形而下者是也。目的是希望能为大家从全局去把握编程提供一定的思路，不为细节所困。本书是一篇散文，形散神不散——以编程为神，以各章节为形；它同时又是一篇科普文章，读起来自然不难理解，甚至是轻松幽默的，不过也不要对这本书期望过高，Part I 是从一个初学者/非 CS 专业学生的角度去感悟计算机编程的，功力自然是比不过各路大神大牛。

## 为什么要整理并公开这个编程笔记

独乐乐不如众乐乐，并且公开之后还可以借助 Google 强大的网络搜索功能方便自己搜索该文档，何乐而不为~

正如许三多当初选择在五班修路一样，我们也抱着同样的信念选择为大家奉献这么一本小册子，虽然自身水平有限，但我还是非常愿意和大家一起分享成长路上所获得的点点滴滴...

大约是在2009年，也就是我当年大一的时候，对计算机各方面了解都不多，上了很久的「计算机文化」和C语言也没搞懂编程到底是在干啥，只是觉得编程是一件很神奇的事，就像是魔法一般，不过雾里看花终隔一层，始终也未能亲身体验它的乐趣。那时多希望有个诸葛能扶一扶我这个阿斗，即便不是卧龙，凤雏也行嘛！我想现在一定也有那么一小撮人抱着这种想法，我只想对你说：「该醒醒了！现在不是立波梦话板块！」**在任何关键时刻，能帮助你的人只有你自己，即便你能找到愿意帮助你的人，那也要你花心思去找不是么？**

作为一个曾经的新手，我深知从新手过渡到老鸟需要拨开天空的乌云，翻山越岭... 正如你们所看到的，书店和网络上充斥着无数的编程教材，同时可以肯定的是，目前已经面世的教材，穷一人一生之力是不可能看完的。在这些书中，有大量的垃圾书，海量的平庸之作，还有少量的精品，而即使是这少量的精品，也不可能看全。既然书这么多，我为什么还要抽时间再来整理一篇呢？拿本书蓝本创作者碧蓝右耳的话来说，他还能多画几张效果图挣俩钱花呢。

情况是这样的，市场上的书虽多，但其中几乎没有几本是面向初学者的。这样的书是如此之少，以至于要去购买或是阅读到它们都是很困难的事。他们要么是一下子告诉你所有的事，好像你能在千分之一秒中突然从菜鸟变成高手，要么就是认为有些事你早就应该知道，拿你当高手看，导致你有一种赤身裸体被抛弃于猛兽横行的非洲旷野的感觉。你还没有穿上衣服走出帐篷，连刀子都没有摸过，他们就试图告诉你草原上有多少可以捕获的猎物以及他们的位置，告诉你几百种武器和毒药的使用秘籍，告诉你两百条以上的陷阱安放要领。你没有经过丝毫的练习，甚至还没有杀死过一只刚出壳的小鸡，他们就要你独自去捕猎数十头饥饿的狮子。这种看似荒谬的情况从过去持续到今天，至今仍然存在。这并不是说那些写教材的朋友都是傻瓜，他们面向的读者是专业的程序员。专业的程序员就像是猎人，他们更换语言就像猎人更换武器一样，不管他使用哪一种武器，捕猎的基本原理没有变化，变化的只是武器的使用方法。对一个成熟的猎人而言，再强调基本原理就没有必要，所以教材编者们对地球人都知道的一些事也就避而不提。

**一个成熟的猎人，他心中的捕猎知识是浑然一体的，武器的选择，野兽的习性，陷阱的安放，怎样做和为什么这样做都结合在一起，没有哪一部分可以独立出来。**一部分一部分的教给别人是极度困难的，要教就只能混杂在一起。编程的情况类似，它的知识体系是一个完整系统，谈到一个问题总会牵扯到另一个，只不过初学者平时遇到的问题太简单了，以至于没有感觉到一个完整知识体系的存在，学起来自然只能是云里雾里。

那么怎么写好一本面向新手的教材呢？个人认为除了介绍一些必要的基础和核心知识外，更重要的是知识背后的思维逻辑，功力欠佳的作者往往很难将其如庖丁解牛般解剖到深入浅出的程度。同时思维上的过程有时只可意会而不可言传，很少有人能很好地注意到思维过程的弥足珍贵。这两方面原因共同导致了好教材难以复制。

### 读者群

读完上边的那几段话你就应该能猜到本书的服务对象了。没错，就是为那些**毫无编程经验但对计算机感兴趣**的人准备的，甚至是**接触计算机不多**的人。这本笔记的目的也正在于此——**为新手介绍一些编程所必需的背景知识和有利的方法，以便于更好地去开启计算机编程这扇神奇的大门。** 如果你认为自己已有一定的编程经验，那你可以把你编程入门的这一段经历与大伙儿分享一下，完善一下这本书或者提 issue 等都是极好的 :)

## 约定、排版及其它

本书中所采用的语言和句法与正规书籍并不完全一样，中英文混排贯穿全文，有些例子只是为说明问题方便而假设，严谨性可能不够，偶尔还会耍点小聪明或是利用编程中常用的符号，例如用 && 代表和，|| 代表或者，更多的东西等着你们自己去挖掘。在这次改版中我尽量做到中英文分离，不必要的中英文混排其实对读者并不太友好。

**尽信书则不如无书**——本笔记仅仅只是把各种资料收集之后再结合我的编程体验进行一次大的整合，但是水平毕竟有限，无法保证所有内容都是正确合理的，信口雌黄和胡说八道仅一步之差，部分评论我尽量保持中立态度。本文引用参考的地方会尽量标注出处以供进一步查阅，同时希望大家阅读的时候带着怀疑的态度。

### 鸣谢

<dl>
  <dt>Blue Auris</dt>
  <dd>中文昵称：碧蓝右耳，本笔记第一部分原材料创作者，前言中提到的 C/C++ FAQ 正是出自他之手，经他本人同意以公用创作许可协议重新发布，我只是做了大量的组织和整合。可以说，没有他的 C/C++ FAQ 就没有这个合辑，谨在此致以崇高的敬意！</dd>

  <dt>Everyone</dt>
  <dd>本书的最终完善者，没有大家的努力与汗水就没有这个优质的笔记。</dd>
</dl>

### License(许可证)

![pic](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

如无特殊说明，本作品采用 [知识共享署名-相同方式共享 4.0 国际许可协议](http://creativecommons.org/licenses/by-sa/4.0/) 进行许可，**欢迎 fork 和传播本文档，但是请注意遵循以上许可协议。**

## Contribution - 如何贡献本文档

如果你发现本文档有任何可以改进之处，欢迎提交你的改进，具体形式有如下几种。

1. 成为本项目的 contributor, 发邮件并把你的 github 账户名告诉我就可以了，我收到邮件后把你的github账号加到 Collaborators 中。
2. 提交 Pull Request, fork本文档的github repo, 发PR给我就好了。
3. 在本文档的github repo处提交issue, 指出有问题的地方。
4. 在 website http://prog-notes.yuanbin.me 相应网页下的disqus评论框中添加评论，指出一些typo或者可以改进的地方。

### 文档格式及编辑工具 - GFM && kramdown Markdown

使用markdown编写，只使用 gitbook 支持的 markdown 语法。gitbook 底层的 markdown renderer 为改动的 kramdown，并增加了GFM支持, 支持的扩展 markdown 语法算是非常多了，具体特性详见 [GitbookIO/kramed](https://github.com/GitbookIO/kramed)

推荐的 markdown 编辑器为 gitbook 自家的 [GitbookIO/editor](https://github.com/GitbookIO/editor), 支持 Windows/Linux/MAC 三大平台，业界良心！但是实测在Arch Linux下可能会出现占用内存过高的情况... OS X 下目前表现还算良好，编辑界面如下图所示，最左边为章节预览，中间为 markdown 编辑框，右边为实时渲染页面，可选择使用全屏模式。

![Gitbook Editor](./images/gitbook_editor.png)

使用其他如 Mou/Vim/Emacs/Sublime Text也不错，但是在新增Chapter/Section时就比较闹心了，嗯，你也可以新建 Section 后再使用其他编辑器编辑。

对 Gitbook 不熟的建议看看 [Gitbook Documentation](http://help.gitbook.com/)，有助于了解 http://algorithm.yuanbin.me 网页上的文字及各章节等是如何编辑及渲染的。

### 章节名及编号

章节等文件名全部采用英文，子章节最多到三级，章节编号无需操心，这种琐事交给 Gitbook 去做就好，如果一定要手动调整，修改`SUMMARY.md`文件，注意其中的缩进关系，Gitbook就指望这个自动给章节编号了。

举个例子，我现在想新增「动态规划」及其子章节。首先在 Gitbook 顶部菜单栏「Book」中找到「Add Chapter」，填入「Dynamic Programming」。好了，在Gitbook左侧章节栏中就能看到新生成的「10. Dynamic Programming」了，左键击之，Gitbook 就会生成「dynamic_programming」目录及本章的说明文件「dynamic_programming/README.md」。如果想在「10. Dynamic Programming」下新增子章节，右键击之，「Add Section」即可，同上，子章节文件名仍然使用英文名，网页显示的标题可以通过 rename 更改再加入中文。

嗯，以上步骤均可直接新建文件夹及操作`SUMMARY.md`文件完成。

### 数学公式

其实代码里是用不着写数学公式的，但是偶尔分析算法可能会用着，用过 LaTeX 的都知道她生成的数学公式有多优雅，以至于不用她来写数学公式都有点不舒服...

这个文档里对于较复杂的数学公式建议使用 LaTeX, 因为托管在gitbook上，所以就用了轻量级的katex插件，没有用重量级的 MathJax。行内和行间公式都是 两个$, 区别在于行间公式写到下一行行首，而行内公式不能写在行首(废话...)。katex非常脆弱，对一些高级的 LaTeX 语法不支持，否则无法编译输出到网站和pdf，尽量用简单的 LaTeX 语法或者不用。

### 正文书写风格

1. 中英文混排贯穿全文，优雅美观起见，尽可能在英文单词前后加空格，这个使能输入法的中英文间加入空格功能就好了。
2. 代码的函数名或短代码建议使用 \`code\`
3. 使用空行进行分段，嗯，markdown通用

通过github合作时，添加/修改内容时给出能看懂的commit就好了。暂时就想到这么多，其实没那么多讲究啦，感觉看着清楚就好，其他想到的再补充。:-)

### 附件及图片引用

图片统一存放在`images`目录下，其他附件存放在`docs`目录下。引用图片链接一般可以通过`![Caption](../images/xxx.png)`声明。

图片体积太大不利于页面加载，建议先压缩后再放入，如果是png图片可考虑使用 [TinyPNG – Compress PNG images while preserving transparency](https://tinypng.com/)

说了这么多，好像真的有人会协作一样... =_= #sigh

## To-Do
