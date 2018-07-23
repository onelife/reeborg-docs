听我说……否则……
=============================

.. index:: ! else

虽然学习编程很有趣，但你也不能总坐在计算机前面。 ``if`` （如果）下雨了，就继续阅读；否则，出去玩吧！（是的，就算你已经当爷爷了！）

两个选择……
--------------

让我们重写一下 ``if`` 开头的这句话：

.. code-block:: python

    if it rains,              # 如果下雨了，
        keep reading,         #   继续阅读；
    otherwise,                # 否则，
        go outside and play   #   出去玩吧！

如果用 Python，我们大概可以写成这样：

.. code-block:: python

    if it_rains():
        keep_reading()
    else:
        go_outside_and_play()

是的，使用 Python 关键字 ``else`` 可以描述更多的选择。让我们用另外一个例子试试。乐跑可以看到它前面是否有墙；观察一下关卡 **周游世界之一** ，你将使用新的条件： ``front_is_clear()`` ——乐跑能用它来判断是否有墙挡在面前。试着使用该函数和 ``if/else`` 写一段程序让乐跑周游世界，大纲如下：

.. code-block:: python


    def move_or_turn():
        if front_is_clear():
            # 做一些事
        else:
            # 做一些别的事

    repeat 42:
        move_or_turn()

.. topic:: 试一试！

    完成上面的大纲，让乐跑攻克 **周游世界之一** 。攻克之后，试试看你能否修改这个程序（增加一行代码）使乐跑在每个转角处都留下一个笑脸。

怎样理解 ``if/else``
------------------------------

我们已经知道了怎样理解 ``def`` 和 ``if`` 语句——等价于插入一个代码块；当 ``if`` 语句的条件为 ``False`` （否）时是例外，此时该代码块被忽略了——等价于被删除了。 ``if/else`` 语句可以被理解为插入多个代码块中的一个。因此，

.. code-block:: python

    move()
    if True:
        turn_right()
    else:
        turn_left()
    move()

等价于

.. code-block:: python

    move()
    turn_right()
    move()

而

.. code-block:: python

    move()
    if False:
        turn_right()
    else:
        turn_left()
    move()

等价于

.. code-block:: python

    move()
    turn_left()
    move()

我们可以用下面的流程图来表示：

.. figure:: ../../flowcharts/else.jpg
   :align: center
