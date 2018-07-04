重复（repeat）
================

.. index:: repeat

我们常常需要固定次数的重复一系列的指令， 使用 Python ，有好几种方法可以做到……但我不想一次介绍太多新概念。所以我只展示其中的一种方法，然后马上开始介绍 ``repeat`` ——一个乐跑的世界所独有的、简单的替代指令。一个标准的实现方法是像下面这样，使用所谓的 **for 循环** ：

.. code-block:: python

    for i in range(n):
        # 在这里
        # 写一些
        # 代码

.. note::

   ``repeat`` 不能在乐跑的世界以外使用。一个 **循环** 表示一个需要重复的代码块。

在乐跑的世界里，我们可以写一个 ``repeat（重复）`` *循环* ：

.. code-block:: python

    repeat n:   # “n”是一个整数
        # 在这里
        # 写一些
        # 代码

例如，下面这段代码可以让乐跑沿着一个正方形的路径行走：

.. code-block:: python

    repeat 4:
        move()
        turn_left()


通过使用 ``repeat`` ，我们可以重写一些函数并去掉重复的指令：

.. code-block:: python

    def turn_right():
        repeat 3:
            turn_left()


因此，``repeat`` 使我们又多了一个方法来消除代码中的重复。

.. topic:: 试一试！

    再次修改一下你的送报纸程序，使用 ``repeat`` 以尽可能的缩短代码。如果你并没有保存上一次的进度，请回到上一节并使用 ``repeat`` 改写程序。

.. admonition:: 写给教育者的内容

    我之所以引入 ``repeat`` 这个额外的 Python 符号的原因是，避免一次介绍四个新概念（循环、变量——比如 ``for _ in range(n)`` 中的 ``_`` 、内建函数——比如 ``range`` ，以及函数的参数）。

    在设计时规定了， ``repeat n`` 中的 ``n`` **必须** 是一个整型立即数（integer literal），而不能是一个变量（variable）。当学生们学过变量以后，他们应该学习更合适的 Python 语法来完成循环并且忘记不标准的 ``repeat`` 。
