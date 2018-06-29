又再回到跨栏！
==================

.. index:: ! elif

乐跑生活在加拿大，这里不只有雨天和晴天，还会有雪花掉下来……一般来说不会同时发生……但是确实发生过……让我们假设每次只有一种情况会发生。那么，乐跑可能面临三种选择：

.. code-block:: python

    if it_rains():      # 如果下雨
        play_indoors()  #    在室内玩
    elif it_snows():    # 如果下雪
        go_skiing()     #    去滑雪
    else:               # 否则
        go_swimming()   #    去游泳（假设天气很暖和）

请注意，第二个选择使用了 ``elif`` ——表示 “else if”（否则，如果……）。若要把其它的天气现象也考虑在内——比如冰雹、打雷、雾、毛毛雨等等，我们可以增加 ``elif: ...`` 代码块。

下面的流程图说明了乐跑所面临的选择：

.. figure:: ../../flowcharts/elif.jpg
   :align: center


怎样理解 ``if/elif/ ... /else`` 语句
----------------------------------------------------

一系列的 ``if/elif/ ... /else`` 语句等价于插入第一个条件被评估为 ``True`` （是）的代码块。因此

.. code-block:: python

    if False:
        do_1()
    elif True:
        do_2()
    elif True:
        do_3()
    else:
        do_4()

等价于

.. code-block:: python

    do_2()

而

.. code-block:: python

    if False:
        do_1()
    elif False:
        do_2()
    elif False:
        do_3()
    else:
        do_4()

等价于

.. code-block:: python

    do_4()

等等。

回到跨栏
---------------

.. index:: front_is_clear()

在上上节课，你写了一段程序可以攻克 **跨栏之一** 和 **跨栏之二** ，但不能攻克 **跨栏之三** 。你的程序可能是这样写的：

.. code-block:: python

   def jump_over_hurdle():
        # 函数的定义

   def move_and_jump_until_done():
        move()
        if at_goal():
            done()
        jump_over_hurdle()

    repeat 42:
        move_and_jump_until_done()

不能攻克 **跨栏之三** 的原因是，我们在写程序的时候，假设跨栏之间的距离是相等的。让我们用新的条件 ``front_is_clear()`` 和关键字 ``else`` 来修改一下。

下面的新程序应该能攻克上面提到的三个关卡，请补全缺失的代码。

.. code-block:: python

   def jump_over_hurdle():
        # 函数的定义

   def run_jump_or_finish ():
        if at_goal():
            # 做一些事
        elif front_is_clear():
            # 做一些事
        else:
            # 做一些事

    repeat 42:
        run_jump_or_finish()

请注意 ``if/elif/else`` 语句的结构，就像之前提到的——在三个独立的选择之中，只有一个会被执行。

.. topic:: 这样做！

    写完上面的程序，并确保能攻克上面提到的三个关卡。

不经任何改动，此程序能攻克 **跨栏之四** 么？……仔细观察一下，你可能会得到否定的答案。运行一下程序以证实你的想法。到我们能用一个程序攻克全部四个 **跨栏** 关卡，还需要花一些时间（ ``while`` ）。
