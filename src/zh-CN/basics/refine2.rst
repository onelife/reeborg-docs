持续改进：第二部分
===================

造成我们在第一部分结尾处遇到的错误的原因是：乐跑放下了一个笑脸，然后——在有机会前进之前，判断它所在的格子里有没有物品。由于该位置有物品，它没有机会执行 ``while`` 循环。或许，我们可以像下面这样，在进行判断之前加一个 ``move()`` ：

.. code-block:: python

    put()
    move()
    while not object_here():
        if front_is_clear():
            move()
        else:
            turn_left()

.. topic:: 试一试！

   在继续阅读之前，请确保前面的程序能完成任务。

世界没那么简单
-------------------

让我们在稍微复杂一点的 **周游世界之二** 再试试刚才的程序。

.. note::

    不要忘了写：

    .. code-block:: python

        from library import turn_right

你会发现结果和我们预想的不一样：乐跑抄了近路，并没有完全绕世界一周。原因是：我们假设乐跑只需前进和左转；而没有考虑到需要右转的情况。所以，乐跑首先需要做的是看看它的右侧还有没有墙，如果没有则右转。下面这段程序正是这个方法 *尝试* ：

.. code-block:: python

    put()
    move()
    while not object_here():
        if right_is_clear():
            turn_right()
        elif front_is_clear():
            move()
        else:
            turn_left()

.. topic:: 轮到你了！

    前面这段程序能够完成任务么？请仔细检查并作出判断。然后运行一下来证实你的想法，或者在你觉得适当的地方进行修改。
