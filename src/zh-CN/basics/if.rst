如果……（就）
======================

如果乐跑能自己进行判断，写程序就会变得非常轻松…… **等等！** 我并不是在告诉你：乐跑可以自己进行判断。

Python 关键字： ``if（如果）``
--------------------------------

.. index:: ! if
.. index:: ! True
.. index:: ! False

.. topic:: 这样做！

    选择一个适当的世界（比如 **空白** ），然后让乐跑执行下面的程序。

.. code-block:: python

    if True:
        move()

    if False:
        turn_left()

``True（是）`` 和 ``False（否）`` 也是 Python 关键字。你可以试试交换它们的位置，然后再运行一遍程序，看看会发生什么。

``if`` 语句
----------------------

所谓的 ``if`` **语句** 其后所跟随的模式和 ``function（函数）`` 类似：:

.. code-block:: python

    def some_name():
        # 代码块

    if some_condition:
        # 代码块

怎样理解 ``if`` 语句
---------------------------------

在介绍函数的时候，我们解释了可以把 **引用** 函数理解为：把该函数所定义的代码块插入到被引用的位置。因此，

.. code-block:: python

    move()
    turn_right()    # 引用函数
    move()

等价于

.. code-block:: python

    move()
    # 代码块开始，和 turn_right() 里面定义的一样
    turn_left()
    turn_left()
    turn_left()
    # 代码块结束
    move()

对于 ``if`` 语句也可以进行类似的理解，只是增加（或者甚至是 **删除** ！）了 *执行条件* 。因此，

.. code-block:: python

    move()
    if True:
        turn_left()
        turn_left()
    move()

等价于

.. code-block:: python

    move()
    turn_left()
    turn_left()
    move()

而

.. code-block:: python

    move()
    if False:
        turn_left()
        turn_left()
    move()

等价于

.. code-block:: python

    move()
    move()

请注意，不要认为这样的删除是永久的：如果我们的程序以某种方式 *循环返回* 并且重复这部分代码，那么 ``if`` 语句每次都会被重新评估以决定是否执行其中的代码块。

我们可以用下面的流程图来表示上面的代码：

.. figure:: ../../flowcharts/if.jpg
   :align: center

可能比你想到的更有用途……
-----------------------------------

.. note::

    用来描述 ``if`` 语句里的、返回值等价于 ``True`` 或 ``False`` 的函数的术语是 **条件（condition）** ：

    .. code-block:: python

       if condition:
           ...

.. index:: object_here(), done()

事先指定的 ``True`` 或 ``False`` 并不能帮助乐跑自己进行判断。然而，乐跑认识的、一些特殊的函数可以帮上忙。其中之一是 ``object_here()`` ，该函数可以告诉乐跑，它所在格子里是否有至少一个物品。例如，当我们让乐跑收集笑脸时，一部分代码可以像这样：

.. code-block:: python

    if object_here():
        take()

观察一下关卡 **笑脸之一** 和 **笑脸之二** 。假设乐跑沿直线前进，当它发现一个笑脸时，所要做的都是：

#. 拾起笑脸
#. 前进一格
#. 把笑脸放下
#. 再前进一格
#. 完成—— ``done()``

在这里，我引入了一条新指令：``done()`` 。实际上，你应该把这条指令理解为是乐跑说的——它宣布自己已经完成任务了。

让我们来写一个在两个世界都能完成任务的程序大纲：

.. code-block:: python

    def move_until_done():
        move()
        if object_here():
            # 做一些事
            # 又做一些事
            # 再做一些事
            # 还再做一些事
            done()

    repeat 42:
        move_until_done()


为什么是42？……嗯，我只是想确保乐跑重复的次数足够多，不管身在哪个世界。目前为止，所有的世界都不大，42应该足够了。 我同意，这看上去不太聪明……我们以后会修改的。

.. topic:: 试试这个！

    把上面的代码复制到编辑框，填上缺失的指令，然后在 **笑脸之一** 和 **笑脸之二** 里测试。

.. admonition:: 写给教育者的内容

    ``object_here()`` 函数返回一个当前格子里的物品类型（字符串格式）列表（list）。比如，当星星（star）和笑脸（token）在同一个格子里时， ``object_here()`` 将返回 ``["star", "token"]`` 或 ``["token", "star"]`` ；当格子里没有任何物品时，将返回空列表。就像你知道的那样，在 ``if`` 语句里，Python 把空列表视为 ``False`` ，把非空列表视为 ``True`` 。

    当一个世界里有很多物品，而我们只对其中的一种感兴趣时，可以在参数里指定物品类型：

    .. code-block:: python

        if object_here("token"):
            take("token")

    ``object_here("token")`` 将只返回空列表或 ``["token"]`` 。
