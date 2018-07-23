惊喜
=========

修改一下我们之前写的程序，把：

.. code-block:: python

    mark_starting_point_and_move()

    while not found_starting_point():
        follow_right_wall()

改写成：

.. code-block:: python

    while not at_goal():
        follow_right_wall()

.. topic:: 试一试！

    在关卡 **跨栏之一** 、 **跨栏之二** 和 **跨栏之三** 里面运行一下该程序。

你会发现该程序——尽管和我们以前写的跨栏程序很不一样，竟然也能完成任务。

.. topic:: 试一试！

    现在，请在关卡 **跨栏之四** 里运行一下。
    
惊喜吗？尽管以前写的程序不能，但现在的程序能完成这个任务！你知道为什么吗？

.. topic:: 再试一试！

    在关卡 **迷宫** 里运行一下同样的程序。

就像你看到的，不管从哪里出发，这个简单的程序都可以让乐跑找到迷宫的出口！

好神奇！
