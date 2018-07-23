``while`` 循环
==============================

.. index:: ! while

当我们需要重复一些指令直到满足一个特定的条件时，Python 给了我们一个简单的方法——使用 ``while`` 关键字。比如，我们想让乐跑持续前进直到遇上一堵墙。以前，我们会这样写：

.. code-block:: python

    def move_until_wall():
        if front_is_clear():
            move()

    repeat 42:
        move_until_wall()

并且希望42这个重复次数足够大，以便能遇上一堵墙。然而，通过使用 ``while`` ，我们可以这样写：

.. code-block:: python

    while front_is_clear():
        move()

就这样！不用猜也不用知道需要重复多少次。

下面是这段简单的程序的流程图：

.. figure:: ../../flowcharts/while.jpg
   :align: center

怎样理解 ``while``
----------------------------

假设我们有下面这段代码：

.. code-block:: python

    while condition():
        do_1()
        do_2()
        do_3()

你可以认为其等价于：

.. code-block:: python

    if condition():
        do_1()
        do_2()
        do_3()
    if condition():
        do_1()
        do_2()
        do_3()
    if condition():
        do_1()
        do_2()
        do_3()
    if condition():
        do_1()
        do_2()
        do_3()
    ....

也就是说只要条件被评估为真（ ``True`` ），其代码块就会被重复。那么，如果条件一直为真（ ``True`` ）会发生什么？——这个代码块将一直被重复，永不停止。

这就糟了。

程序员会把被重复的代码块称作 **循环（loop）** ：指令从代码块里的第一条（ ``do_1()`` ）开始执行，直到最后一条（ ``do_3()`` ），然后 **循环返回** 到代码块开始处的条件判断，看看条件是否仍然满足。如果仍然满足，则再重复一遍。如果条件永远不为假（ ``False`` ），代码块将一直被重复，其结果就是一个 **无限循环（infinite loop）** 。

注意：你应该确保循环条件能在某个时刻变为假（ ``False`` ）。

回到跨栏！
----------------

.. topic:: 轮到你了！

    回到 **跨栏之一** 、 **跨栏之二** 和 **跨栏之三** ，使用 ``while`` 代替 ``repeat`` ，用一段程序攻克全部三个关卡。

.. hint::

    你可以使用下面的程序大纲：

   .. code-block:: python

       def jump_over_hurdle():
           # 函数的定义

       def run_or_jump ():
           # 函数的定义 definition

       while not at_goal():
           run_or_jump()

就这样！再也不用猜测要重复多少次了！从现在开始，请只有在知道一个函数 **确切的** 重复次数时才使用 ``repeat`` 。
