

重温送报纸
============================

让我们回到名为 **送报纸之零** 的世界，重温一下给 Richard Pattis 送报纸的任务。下面是该任务的一种解决方案并包含了注释。

.. code-block:: python
   :linenos:

    take()  # 北极星报

    # 爬上一层楼
    turn_left()
    move()
    turn_left()
    turn_left()
    turn_left()
    move()
    move()

    # 爬上两层楼
    turn_left()
    move()
    turn_left()
    turn_left()
    turn_left()
    move()
    move()

    # 爬上三层楼
    turn_left()
    move()
    turn_left()
    turn_left()
    turn_left()
    move()
    move()

    put()   # 放下报纸

    # 调头
    turn_left()
    turn_left()

    # 爬下一层楼
    move()
    move()
    turn_left()
    move()
    turn_left()
    turn_left()
    turn_left()

    # 爬下两层楼
    move()
    move()
    turn_left()
    move()
    turn_left()
    turn_left()
    turn_left()

    # 爬下三层楼
    move()
    move()
    turn_left()
    move()
    turn_left()
    turn_left()
    turn_left()

这个解决方案很长……并且在打字的时候很容易出错。我们注意到：里面有很多重复的代码片段，可以提取出来做成函数。我们已经定义过 ``turn_right()`` 和 ``turn_around()`` ，现在让我们再多定义一些。

.. code-block:: python
   :linenos:

    from library import turn_right, turn_around

    def climb_up_one_floor():
        turn_left()
        move()
        turn_right()
        move()
        move()

    def climb_up_three_floors():
        climb_up_one_floor()
        climb_up_one_floor()
        climb_up_one_floor()

    def climb_down_one_floor():
        move()
        move()
        turn_left()
        move()
        turn_right()

    def climb_down_three_floors():
        climb_down_one_floor()
        climb_down_one_floor()
        climb_down_one_floor()


    # === 定义结束 ===

    take()  # 北极星报
    climb_up_three_floors()
    put()   # 放下报纸
    turn_around()
    climb_down_three_floors()

上面的每一个函数都不超过五行。和验证一大段指令（比如第一段程序）相比，验证上面的每一个函数能否够按照预期工作，很轻松。一旦确定了这些函数都能够正确工作，那么我们再多写五行便可完成任务，而且同样容易验证。综上所述，利用函数来避免重复，可以使我们写出更短、更具可读性的程序。

.. topic:: 轮到你了！

    写出上面的程序并确保其工作正确。完成之后，你就可以学习另外一个能把程序写得更简单的技巧了。

由于 ``climb_up_one_floor()`` 、``climb_up_three_floors()`` 等函数都是专门为单一的关卡写的，把它们放在库里可能 **不合适** 。你也不希望库里有太多的函数，不然就记不住了。只有在不同的程序里被多次使用到的函数才适合被放进库里。
