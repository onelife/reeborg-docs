
调头
===========

除了让乐跑向右转，你 *可能* 还需要让它调头。我所谓的调头就是让乐跑向后转、转向它来的方向。我们可以像下面这样定义一个 ``turn_around()`` 函数：

.. code-block:: python

    def turn_around():
        turn_left()
        turn_left()

试试吧！

再回到 ``turn_right()``
------------------------

还记得 ``turn_right()`` 么？再看一次：

.. code-block:: python

    def turn_right():
        turn_left()
        turn_left()
        turn_left()

请注意，前面的两个指令就是 ``turn_around()`` 函数所定义的内容。当这种情况发生时，我们必须要记起规则三：

.. important::

    规则三
        写计算机程序时，不要重复你自己。我再强调一遍： **不要重复你自己！**

我们现在有了重复的指令。当 ``turn_right()`` 已经很简单的时候，一个好的编程实践是：把部分代码替换成一个简单的函数。因此，我们应该像下面这样重写 ``turn_right()`` :

.. code-block:: python

    def turn_right():
        turn_around()
        turn_left()

这背后的想法是：函数越短，出错的可能性就越小。此外，一旦我们有了经过严格测试的、没有问题的函数，我们就应该在编写比较长的函数时尽可能地使用到它。我承认，这是一个很傻的例子……但此时，我还没有一个更复杂的例子来表达这个重要的概念。

.. topic:: 轮到你了

    定义一个 ``step_back()`` 函数来抵消 ``move()`` 函数的效果。也就是说：

    .. code-block:: python
    
        # 假设当前的坐标为 x，y
        move()
        step_back()
        # 此时应该回到和之前同样的位置
        # 并且和之前面朝的方向一致

    请一定要测试你的程序！

不要看提示，除非你觉得绝对做不出来！

.. hint::

   在定义 ``step_back()`` 时，你可能要用到 ``turn_around()`` 两次。
