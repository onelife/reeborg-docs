重温一些关卡
==========================

是时候解决一些以前没能攻克的关卡了。

使用 ``while`` 、 ``if`` 、 ``else`` 等等，你应该可以写出能够解决多种问题的程序。在写程序时，请记住以下三点：

#. 牢记规则二；在给函数起名字时，请选择能够描述你正在试图解决的问题的名称
#. 遵守规则四中原则：从解决简单的问题开始，然后归纳你的解决方案，使其可以应用到更多的问题上
#. 牢记规则三；尽量避免代码重复

现在，请牢记规则一……然后，完成下面提到的 **全部** 的关卡。

.. important::

    请保存你的解决方案，以后可能用得上。


收获季之前
-----------------

关卡 **大丰收之三** ，发生在乐跑在菜园里播种后不久。有一些胡萝卜种子很好的发芽了；另外有一些在同一个格子里长出了两、三个芽；还有一些没有发芽。请让乐跑移除多长出来的芽，并且在没有种子发芽的地方补种。


.. topic:: 这样做！

    写一段程序来完成前面描述的任务。


丰收时刻
----------------

前面的工作进行的很顺利（希望是这样！），生长季结束了、丰收季来临了。请选择关卡 **大丰收之一** 或 **大丰收之二** ，让乐跑收集所有的胡萝卜。你需要要用一个程序来完成这两个任务。


暴风雨
--------------

在美丽而晴朗的一天，乐跑和朋友一起在外面玩儿。忽然，天上开始下起了雨。乐跑想起家里的窗户还没关，于是就跑回家。但走到门前时，它停住了，因为不知道要怎么做。

.. index:: wall_on_right(), right_is_clear()

.. topic:: 这样做！

    让乐跑关上窗户。可以使用 ``build_wall()`` 、 ``wall_on_right()`` 或 ``wall_in_front()`` 指令，但 **不要** 使用 ``right_is_clear()`` 或 ``front_is_clear()`` 指令。当关好窗户后，乐跑要回到门口看雨，等雨停了才能再出去玩。这就是关卡 **下雨之一** 的任务。

轮到乐跑的朋友了
------------------------

鹅蛋（Erdna）是乐跑的朋友，在关卡 **下雨之二** 里可以看到，它有一个更大的房子。刚开始下雨的时候，鹅蛋正在外面和乐跑玩儿。请让鹅蛋也关好窗户。

.. topic:: 试一试！

    写一段程序来让乐跑和鹅蛋都关好窗户，依然不要使用  ``right_is_clear()`` 或 ``front_is_clear()`` ……这可能会有点棘手。

.. hint::

    机器人可能需要多走几步，来判断一个地点是否有窗户。比如先往前走一格，观察一下；根据情况再向后转、走回去、关窗户。

.. topic:: 再做一遍！

    这一次，可以使用 ``right_is_clear()`` 或 ``front_is_clear()`` ，再加上 ``wall_on_right()`` 或 ``wall_in_front()`` 指令，写一段程序让乐跑和鹅蛋都关好窗户。由于得到了更多的、直接的信息，这次机器人所花的步骤（ ``move()`` 或 ``turn_left()`` ）数量应该会下降。


暴风雨过后
---------------

.. index:: carries_object()

昨晚的风刮得很猛，所以乐跑的房子周围到处是落叶。它的家长叫它去清理通往大马路的小径（ **暴风雨之一** ）和车道（ **暴风雨之二** ）。

.. topic:: 轮到你了！

    让乐跑收集全部的落叶、放进堆肥箱，并且使用 ``build_wall()`` 指令盖好盖子。你可以用 ``if`` 或 ``while`` 语句加上测试条件 ``carries_object()`` 来判断乐跑是否携带了物品（落叶）。


更多整理院子的工作！
--------------------

乐跑的家长为它所做的工作感到很骄傲，所以把清理后院的工作也交给了它（ **暴风雨之三** ）。请让乐跑收集全部的落叶并放进堆肥箱。

.. topic:: 轮到你了！

    写一段程序来攻克全部三个 **暴风雨** 关卡。


找到世界的中心
------------------

观察一下关卡 **世界的中心之一** 和 **世界的中心之二** 。

.. topic:: 这样做！

    写 **一段** 程序让乐跑把一个笑脸放在它所在的世界的中心。请从简单的关卡（ **世界的中心之一** ）开始，逐步改进以解决更复杂的问题。请注意这是一个很有挑战性的任务。

.. hint::

    乐跑带了两个笑脸，你可以在一条直路的两端各放一个。然后，拾起一个笑脸、前进一格再放下；走到另外一个笑脸处，拾起来、前进一格再放下。如此往复，直到两个笑脸都放在了相同的位置。这个位置就是这条直路的中心位置。当乐跑在一个一维的空间（比如一条水平的直路）里找到中心后，以此为起点，找到另外一维（比如一条垂直的直路）的中心，这样就找到了这个二维的世界的中心。
