[toc]

# How To Learn Hacking

## 什么是黑客攻击？

The “hacking” we'll be talking about in this document is exploratory programming in an open-source environment. If you think “hacking” has anything to do with computer crime or security breaking and came here to learn that, you can go away now. There's nothing for you here.

我们将在本文档中讨论的“黑客”是在开源环境中进行探索性编程。如果您认为“黑客攻击”与计算机犯罪或破坏安全有任何关系并且是来这里学习的，那么您现在可以离开了。这里没有适合你的东西。

Hacking is primarily[[1\]](http://www.catb.org/~esr/faqs/hacking-howto.html#ftn.idm45418026495008) a style of programming, and following the recommendations in this document can be an effective way to acquire general-purpose programming skills. This path is not guaranteed to work for everybody; it appears to work best for those who start with an above-average talent for programming and a fair degree of mental flexibility. People who successfully learn this style tend to become generalists with skills that are not strongly tied to a particular application domain or language.

Hacking 主要是[[1\]](http://www.catb.org/~esr/faqs/hacking-howto.html#ftn.idm45418026495008)一种编程风格，遵循本文档中的建议可能是获得通用编程技能的有效方法。这条路不能保证对每个人都有效；它似乎最适合那些一开始就具有高于平均水平的编程天赋和相当程度的思维灵活性的人。成功学习这种风格的人往往会成为通才，其技能与特定应用领域或语言没有紧密联系。

Note that one can be doing *hacking* without being a *hacker*. “Hacking”, broadly speaking, is a description of a method and style; “hacker” implies that you hack, and are also attached to a particular [culture](http://catb.org/~esr/faqs/hacker-howto.html) or historical tradition that uses this method. Properly, “hacker” is an honorific bestowed by other hackers.

请注意，一个人可以在不成为*黑客的情况下进行hacking。“ hacking ”，广义上，是对一种方法和风格的描述； “hacker”意味着您进行hack，并且还依附于使用此方法的特定[文化或历史传统。](http://catb.org/~esr/faqs/hacker-howto.html)准确地说， “黑客”是其他黑客赋予的尊称。

Hacking doesn't have enough formal apparatus to be a full-fledged methodology in the way the term is used in software engineering, but it does have some characteristics that tend to set it apart from other styles of programming.

黑客没有足够的正式工具来成为软件工程中使用该术语的方式的成熟方法，但它确实具有一些特征，倾向于将其与其他编程风格区分开来。

- *Hacking is done on open source.* Today, hacking skills are the individual micro-level of what is called “open source development” at the social macro-level. [[2\]](http://www.catb.org/~esr/faqs/hacking-howto.html#ftn.idm45418026909600) A programmer working in the hacking style expects and **readily（adv.乐意地; 快捷地;轻而易举地; 便利地; 容易地）** uses peer review of source code by others to **supplement（增补，补充; ）** and amplify his or her individual ability.

- Hacking是在开源上完成的。*今天，黑客技能是社会宏观层面所谓的 “开源开发”的个人微观层面。[[2\]](http://www.catb.org/~esr/faqs/hacking-howto.html#ftn.idm45418026909600)以黑客风格工作的程序员期望并乐于使用他人对源代码的同行评审来补充和扩大他或她的个人能力。
- *Hacking is lightweight and exploratory.* Rigid procedures and elaborate a-priori specifications have no place in hacking; instead, the tendency is try-it-and-find-out with a rapid release tempo.
- *黑客攻击是轻量级和探索性的。* 严格的程序和详尽的先验规范在黑客中没有立足之地；取而代之的是，趋势是通过快速发布节奏进行尝试和发现。
- *Hacking places a high value on modularity and reuse.* In the hacking style, you try hard never to write a piece of code that can only be used once. You bias towards making general tools or libraries that can be specialized into what you want by freezing some arguments/variables or supplying a context.
- *黑客非常重视模块化和重用。* 在黑客风格中，你努力不写一段只能使用一次的代码。您倾向于通过冻结一些参数/变量或提供上下文来制作可以专门用于您想要的东西的通用工具或库。
- *Hacking favors scrap-and-rebuild over patch-and-extend.* An essential part of hacking is ruthlessly throwing away code that has become overcomplicated or crufty, no matter how much time you have invested in it.
- *与修补和扩展相比，黑客更喜欢废弃和重建。*黑客的一个重要部分是无情地丢弃变得过于复杂或粗糙的代码，无论您在上面投入了多少时间。

The hacking style has been closely associated with the technical tradition of the Unix operating system[[3\]](http://www.catb.org/~esr/faqs/hacking-howto.html#ftn.idm45418026904272)

黑客风格与 Unix 操作系统的技术传统密切相关[[3\]](http://www.catb.org/~esr/faqs/hacking-howto.html#ftn.idm45418026904272)

Recently it has become evident that hacking blends well with the “agile programming” style. Agile techniques such as pair programming and feature stories adapt readily to hacking and vice-versa. In part this is because the early thought leaders of agile were influenced by the open source community. But there has since been traffic in the other direction as well, with open-source projects increasingly adopting techniques such as test-driven development.

最近很明显，黑客与 “敏捷编程”风格很好地融合在一起。结对编程和专题报道等敏捷技术很容易适应黑客，反之亦然。部分原因是敏捷的早期思想领袖受到了开源社区的影响。但此后也出现了另一个方向的流量，开源项目越来越多地采用测试驱动开发等技术。

## Stages of Learning How To Hack

## 学习如何破解的阶段

Learning to compose music has three stages. First, you have to learn the basic **mechanical 机械（学）的; 机器的;无思想的** technique of an instrument — fingering and how to play scales. Then you have to train your ear to understand musical patterns. Finally, you must learn how to recombine musical patterns into original creations. Hacking is similar.

学习作曲分三个阶段。首先，您必须学习乐器的基本机械技术——指法和如何演奏音阶。然后你必须训练你的耳朵来理解音乐模式。最后，您必须学习如何将音乐模式重新组合成原创作品。黑客攻击是相似的。

The hacking equivalent of fingering is learning the capabilities of programming languages, and the mechanics of using tools like editors, interpreters, and compilers. (If you don't understand these terms, see [The Unix and Internet Fundamentals HOWTO](http://www.tldp.org/HOWTO/Unix-and-Internet-Fundamentals-HOWTO/index.html).) We won't cover those mechanics here as they vary too much according to what language you're using. Tutorials for all the languages you might want to use are available on the Web; use a search engine.

相当于指法的是学习编程语言的hacking能力，以及使用编辑器、解释器和编译器等工具的技巧。（如果您不理解这些术语，请参阅[ The Unix and Internet Fundamentals HOWTO](http://www.tldp.org/HOWTO/Unix-and-Internet-Fundamentals-HOWTO/index.html)。）我们不会在这里介绍这些机制，因为它们因您使用的语言而异。您可能想使用的所有语言的教程都可以在 Web 上找到；使用搜索引擎。

The equivalent of playing scales is writing small programs, alone. Unfortunately, playing scales (a) doesn't teach you anything about music, and (b) is boring as hell. Similarly, writing toy programs doesn't tend to teach you much about hacking, and (b) will tend to de-motivate you unless the program immediately solves a problem you care about.

演奏音阶相当于一个人写小程序。不幸的是，演奏音阶 (a) 不会教给你任何关于音乐的知识，而且 (b) 非常无聊。同样，编写玩具程序不会教给你很多关于黑客攻击的知识，并且 (b) 往往会使你失去动力，除非该程序立即解决你关心的问题。

Most formal programming instruction gets to playing scales and stops. Thus, it tends to produce coders who are poor at collaborating with each other and have the equivalent of no ear for music — a poor feel for software design and architecture.

大多数正式的编程指令都会涉及到演奏音阶和音阶。因此，它往往会培养出不善于相互协作的编码员，相当于没有听音乐的耳朵——对软件设计和架构的感觉很差。

## 增量黑客循环

There is a better way to learn. I call it the incremental-hacking cycle.

有更好的学习方法。我称之为增量黑客循环。

1. First, pick a program that does something you are interested in. Ideally, it should be a program you use regularly and have opinions about. The next best thing is a program you don't normally use, but that does something you think is interesting. For this learning method to work, you should avoid trying to hack on code that bores you.

   The program you choose doesn't have to do anything serious. Many programmers have honed their skills by improving games that they enjoyed. The only drawback to this is that modern games are often quite large and complicated, and may be beyond the grasp of a raw beginner. For this reason, you may want to investigate one of the classic text-oriented games that still survive; nethack is a prime example, and there are many others.

   首先，选择一个您感兴趣的程序。理想情况下，它应该是您经常使用并且有意见的程序。下一个最好的事情是你通常不使用的程序，但它做了你认为有趣的事情。为了使这种学习方法起作用，您应该避免尝试破解让您感到**厌烦**的代码。

   您选择的程序不必做任何严肃的事情。许多程序员通过改进他们喜欢的游戏来磨练他们的技能。唯一的缺点是现代游戏通常非常庞大和复杂，初学者可能无法掌握。出于这个原因，您可能想要研究一款仍然存在的经典文本游戏；nethack 是一个典型的例子，还有很多其他例子。

2. If you don't already know the program, learn how to use it. Read the documentation. Develop a mental model of how it works.

   如果您还不知道该程序，请了解如何使用它。阅读文档。开发一个关于它如何工作的心智模型。

3. Pick a small feature to change or add.

   选择要更改或添加的小功能。

4. Search the code until you find the part you need to modify.

   搜索代码，直到找到需要修改的部分。

   Note: you should specifically *not* try to read the entire program. You will just exhaust and frustrate yourself if you do that. Instead, use the module structure of the code to zero in on just the part you need to understand. Along the way, you will learn things about how the whole program fits together.

   注意：你*不*应该试图阅读整个程序。如果你这样做，你只会筋疲力尽并感到沮丧。相反，使用代码的模块结构将您需要理解的部分归零。在此过程中，您将了解到整个程序是如何组合在一起的。

   It's a good exercise to add **explanatory 解释性的，说明性的** comments and notes to the code as you figure out things about it. This will help your memory, and will help you organize your thoughts as well.

   当您弄清楚代码的相关内容时，向代码添加解释性注释和注释是一个很好的练习。这将有助于你的记忆，也将帮助你组织你的想法。

5. Make, test, debug, and *document* your change.

   制作、测试、调试和*记录*您的更改。

   Documenting your change is important. If you develop the habit of doing this early, you'll produce much higher-quality work.

   记录您的更改很重要。如果你及早养成这样做的习惯，你会产出更高质量的作品。

6. 将您的更改作为补丁发送给程序维护人员。请参阅 [Software Release Practice HOWTO](http://www.tldp.org/HOWTO/Software-Release-Practice-HOWTO/index.html)以获得有关如何以有效和礼貌的方式执行此操作的提示。

   我最初将此描述为可选步骤；一位聪明的朋友指出，我可能不应该这样做。在你的乐器上单独弹奏对于练习来说非常好，但是当其他人听到其中的创造力时，音乐就完成了并得到了验证。独自在电脑上写东西同样有利于练习，但当其他人*使用你写*的东西时，黑客就完成了。真实世界的测试很重要。

   有时（通常是刚开始时）您的补丁会被拒绝。你需要学会应对这种情况。这并不意味着您注定要失败。通常它的意思是你没有足够仔细地阅读代码，或者（就像通常一样）你错过了一些关于你试图贡献的开发团队的文化和实践的重要信息。这些错误是可以修复的。

7. 现在，问问自己：我理解整个程序吗？

   如果是，你就完成了。如果不是，回到第 3 步。这一次，选择一个不同的、也许稍微困难一点的事情来改变。

这个练习的重点是学习如何偷偷理解程序的问题，而不是试图一次解决所有的复杂性。当您多次执行此循环时，您将逐渐在脑海中形成对整个程序组合方式的更完整的表示。在某个时候，你会达到一个你完全理解的门槛——或者无论如何，无论你的最终目的是什么，都已经足够了。

## 培养你的设计感

要训练自己，从小做起。如果可能，首先在非常小的程序或脚本（10-50 行）上练习增量黑客循环。这些可能很难找到，因为任何用途的大多数程序都比这大。大多数这么小的程序都是 shell、Perl、Python 或 Tcl 中的脚本；这是在网上搜索他们时要寻找的特征。

当你在几个非常小的程序上完成了增量黑客循环（或者如果你很不幸没有找到任何合适的非常小的程序），在稍大的程序上尝试一下。寻找 100-500 行范围内的代码库。

当你掌握了那个级别之后，再去量级，1000-5000行。当您掌握 1K-5K 级别时，您将进入通常被认为是熟练程序员的能力范围的底端。

在 1K-5K 级别或之前，您应该偶尔开始注意到您渴望更改程序的 *结构*或*组织*，而不仅仅是其功能。您可能会发现自己在想 “这段代码很丑”，并且觉得要让它更漂亮、更干净。

发生这种情况时，*请注意*。这是你试图唤醒的设计感。不要急于修补另一个功能。相反，开始探索让您在更高层次上产生这种渴望的程序。 *现在*可能是尝试阅读所有代码的好时机，但如果你不能，也不要太担心；大多数程序都太大太乱，无法一次将它们全部吞噬。只需尝试掌握清理事物所需的知识即可。

您现在正在进入学习破解的中间部分。这不仅涉及改变表面可见的功能，还涉及进行所谓的“重构” ——在内部重新组织代码，使其更简洁，并具有更好的架构（更好地隐藏数据、缩小不同部分之间的接口、模块之间的功能分离更多）。

一旦您的设计感（相当于您的音乐耳朵）被激活，您通常会发现您开始重构您工作的每个程序，就像在增量黑客循环中的第三或第四次一样快。

事实上，这正是熟练的黑客通常学习大型程序代码的方式——通过修补、重构和重写，直到他们弄明白发生了什么。你做小的改变是为了学习如何做大的改变。

如果你成功地重构了三个或四个大型系统，你不仅会发展出强大的编程技能，你还将走上更难得和更强大的道路：成为一名软件架构师，一个可以对大型软件系统进行原始设计的人。

这是*我所知道的*让初出茅庐的软件架构师训练他们的设计感的唯一方法。这可能是唯一的方法。

## 原创

在我与音乐的类比中，我说过你最终需要学习如何将音乐模式（你通过听音乐和练习表演学到的）重新组合成原创作品。我谨慎地选择了这种描述创造力的方式，因为它更适用于软件而不是音乐。

在您阅读并吸收大量代码的教训之前，您的头脑中可能没有您需要的模式库，您需要在比非常小的规模更大的规模上发挥创造力。进行增量黑客循环的一个目的是让自己沉浸在大量代码中——在不断增加的复杂性范围内——在为你提供继续阅读动力的情况下。

最终你将领导小组项目并完成完全原创的工作。不要觉得你必须匆忙或强迫它；如果你给你的技能时间来成熟，你的第一篇原创作品会更好。通过有效地为现有的开源项目做出贡献，您将学习运行自己的项目所需的技能（包括沟通技巧）。



------

[[1\]](http://www.catb.org/~esr/faqs/hacking-howto.html#idm45418026495008)破解软件以外的东西当然是可能的，而且创客文化中的人也这样做。但是“黑客”这个*词* 起源于那些修补软件的人，并且仍然从那里辐射出去。再说了，作者还真没资格写学习其他种类。