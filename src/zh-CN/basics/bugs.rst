捉虫！
==========

没人喜欢谈论计算机臭虫（bugs）！但不走运的是，你必须学习，特别是学习怎样对付它。

这节课比之前的课略长，但我建议你至少完整的阅读一次。

臭虫是什么？
--------------

在计算机领域里， **臭虫** 这个词最开始是和哈佛大学的一台 Mark II 计算机的一个真实故事联系在一起的：一只蛾子使该计算机停止了工作。一个由知名的计算机科学家、数学家、年轻的海军军官—— Grace Murray Hopper 领导的团队找到了这个问题。Grace Hopper 博士后来逐渐升任成为了美国海军上将。

这只蛾子后来被保留，并且粘在了 Hopper 的日志里，见下图。有趣的是，你可以看到，日志里有一行笔记写着：“第一次发现真正的臭虫。”（"First actual case of bug being found."）

|image0|

图片剪切自 `美国海军历史中心（U.S. Naval Historical Center）
<https://www.history.navy.mil/content/history/nhhc/our-collections/photography/numerical-list-of-images/nhhc-series/nh-series/NH-96000/NH-96566-KN.html>`__ 的公开档案。


实际上，在学术语境里的臭虫（bug）这个词，牛津英语词典认为和 Thomas Edison （托马斯爱迪生）有关。根据牛津词典的解释，下面这段话出自1889年3月11日的颇尔商城公报（Pall Mall Gazette）：

    我听说爱迪生先生前两个晚上一直在他的留声机里寻找“一只臭虫”。这是一种表达方式——表示某人正在解决一个困难的问题。这里用一只虚构的昆虫来做比喻，说它藏了起来并且造成了很多麻烦。（Mr. Edison, I was informed, had been up the two previous nights
    discovering 'a bug' in his phonograph - an expression for solving a
    difficulty, and implying that some imaginary insect has secreted
    itself inside and is causing all the trouble.）

这样看来，“臭虫”一词最初确实指的是一个昆虫，只不过是虚构的昆虫。

不走运的是，计算机臭虫不是昆虫，更不是虚构的。

对付臭虫
-----------------

在计算机领域里，一个臭虫表示一个造成程序不按照预期的行为运行的错误。如果你写了一个计算机程序，那么里面早晚会有臭虫——每个人都如此。好的程序员一旦发现他们的程序不能按照预期执行，就会马上开始寻求“移除”或者“修正”臭虫。

不怎么好的程序员会说，“臭虫”不是真正的错误，只是一种“功能”。**你** 要做一个好的程序员，不要像乐跑的作者一样——在他的程序里到处是臭虫。

.. figure:: ../../images/reeborg_costume.jpg
   :figwidth: 40%
   :align: right

   全尺寸的乐跑（美国新泽西州）

   *图片来自 A. Judkis。*
   
#. 乐跑曾经漏过油。漏油对环境有害，也给乐跑造成了不便——它在不急着完成任务的时候，不得不去补充燃料。乐跑的作者狡辩说这是一个功能，因为这迫使你跟随着乐跑的脚步——就像任何程序员那样，学习“跟踪”一个程序。后面你将会学到怎么修理漏油问题。更高阶的跟踪臭虫的技术——比如使用 *调试器* ，超出了本教程的范围。
#. 乐跑的转向机构没有搞好： 它只能左转。乐跑的作者又一次狡辩说这是一个功能，因为这给了你一个学习 **函数** 的机会，虽然乐跑表示不同意。你很快会学到一种 *补救方法* 让乐跑可以右转，虽然是一种很耽误工夫的做法。再晚一点，你将会学到如何从根本上解决这个问题——让乐跑可以做真正的右转，就像做左转那样。
#. 乐跑有个罗盘，让它可以知道自己所面对的方向。但再一次不走运的是，让乐跑从罗盘里得到信息的程序有臭虫：它只能告诉乐跑北在哪儿……或者北不在哪儿。和之前一样，你得先学习实现补救的方法，然后才学习长久修复的方法，以便让乐跑摆脱作者所谓的“功能”。
#. 当有一堵墙挡在面前时，乐跑能看到，并且还能把头转向右侧，看看是否也有一堵墙。然而，有个软件上的“毛刺儿（glitch）”（软件开发商们用来避免承认其产品有臭虫的另外一种托辞）导致乐跑在把头转向左边时，不能正确识别是否有墙存在。

有时，为了找到出现臭虫的原因，你必须打断程序的正常流程。为此，你可以做一次或多次以下的操作：

.. index:: pause()

#. 你可以 *暂停（pause）* 程序：当程序运行的时候，按 **pause**
   按钮。这和人们说的，在计算机程序里设置一个 *断点（breakpoint）* 类似。
#. 你也可以在程序的任意一行敲进 ``pause()`` 指令来代替按暂停按钮。乐跑会停下，等到你许可时才继续。
#. 你可以 *步进执行（step through）* 程序：按 *执行一条指令然后暂停（execute one instruction and pause）* 或者 **步进（step）** 按钮，每按一次只执行一条指令。即将被执行的指令的上一条指令会被默认高亮，你可以按代码编辑框上方的按钮来关闭高亮。
#. 在程序的任意一行，你可以改变程序的执行速度（执行两条指令之间的时间间隙）。稍后，我会解释怎么做。
#. 在程序的任意一行，你可以让乐跑写下一些信息。还是稍后，我会解释怎么做。
#. 最后，在任意位置，你可以按 **停止（stop）** 按钮让乐跑停下来。不走运的是，如果你制造了一个所谓的无限循环，这个按钮可能就不管用了——这超出了乐跑的控制范围。如果最糟的情况出现了，你随时可以重新加载该网页。

.. |image0| image:: ../../../src/images/first_bug.jpg
