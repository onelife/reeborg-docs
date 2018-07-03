这不……是真的！
================

.. index:: ! not

乐跑有些失望。天上既 **没有** 下雨，也 **没有** 下雪。但它也不能出门，因为要练习跨栏。

为什么我要这么说话？因为乐跑在等你学习 Python 关键字 ``not`` （没有、不）。

到了学习否定的时间了
--------------------

在写 Python 程序时，我们可以用 ``not True`` 来表示对某个条件的否定，它是 ``False`` （否、假）的代名词。同样的，``not False`` 等价于 ``True`` （是、真）。

请让乐跑高兴起来
--------------------------

你已经写了一个能让乐跑跨栏的程序，其中的部分代码可能是这样的：

.. code-block:: python

   def run_jump_or_finish ():
        if at_goal():
            # 做一些事
        elif front_is_clear():
            # 做一些事
        else:
            # 做一些事

.. topic:: 试试这个！

    使用 ``not`` 关键字 **和** ``if/elif/else`` 语句进行组合，再写三个不同版本的跨栏程序，以便让乐跑高兴起来。

你可以使用下面的三个例子，请注意 ``not`` 关键字的位置 **以及** 每个代码块中的内容：

.. code-block:: python

   # 第一个版本：

   def run_jump_or_finish ():
        if at_goal():
            # 做一些事
        elif not front_is_clear():
            # 做一些事
        else:
            # 做一些事

   # 第二个版本……有点棘手

   def run_jump_or_finish ():
        if not at_goal():
            if front_is_clear():
                # 做一些事
            else:
                # 做一些事
        else:
            # 做一些事

   # 第三个版本

   def run_jump_or_finish ():
        if not at_goal():
            if not front_is_clear():
                # 做一些事
            else:
                # 做一些事
        else:
            # 做一些事

另外一种方式
--------------

.. index:: wall_in_front()

你刚刚看到：改变 ``if/elif/else`` 语句中条件的出现顺序，我们仍然可以完成同样的任务。两个不同的程序员经常使用不同的策略，但得到相同的结果。还有很多其它的方式，使不同的程序员写出不同、但等价的程序——比如，使用不同的函数。

``front_is_clear()`` 函数可以告诉乐跑是否有一堵墙挡住了它的路。所谓的墙，也可能是 **水** 、 **砖墙** 、 **篱笆** 等等，我们以后都会碰到。有一个函数是专门判断有没有墙的，叫做 ``wall_in_front()`` ，你来猜猜它的作用。

.. topic:: 试试这个！

    用 ``wall_in_front()`` 代替等价的 ``not front_is_clear()`` 改写程序。
