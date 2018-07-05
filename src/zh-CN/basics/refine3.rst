持续改进：第三部分
===================

你应该已经知道了前面的程序有错误：当旁边没有墙时，乐跑就会陷入无限循环。我们需要让它在右转之后 ``move()`` （前进），就像下面这样：

.. code-block:: python

    put()
    move()
    while not object_here():
        if right_is_clear():
            turn_right()
            move()
        elif front_is_clear():
            move()
        else:
            turn_left()

更复杂的世界
----------------------

.. topic:: 另外一个世界！

    现在，观察一下关卡 **周游世界之三** ，想一想我们的程序是否仍旧能完成任务。


就像你猜测的那样，很不走运，答案是否定的。在阅读下一节之前，请先尝试找出原因。
