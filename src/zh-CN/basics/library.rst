
使用库（Library）
=================

.. index:: ! from ... import

当要使用一些在别的程序里定义过的函数时，一个程序员并不会重新定义它们；取而代之的是，他会把这些函数放在一个特别的、名为 **库（libraries）** 的程序里，这样就可以在别的程序里面使用了。

你还会使用 ``turn_right()`` 函数 **很多次！** 为了避免每次都重写一遍（记住规则三），你应该只（再）写 **一次** ，但不是写在代码编辑框的 **Python Code（代码）** 标签页里，而是点击并写在 **library（库）** 标签页里。对了， ``turn_around()`` 函数也应该写在那里。

.. image:: ../../../src/images/library.png


现在，当你要使用库里的函数时，只需在 Python 代码标签页里的单独的一行写下 ``from library import`` （后面跟以逗号 ``,`` 分割的函数名）。

.. topic:: 这样做！

   在库标签页里定义好 ``turn_right()`` 和 ``turn_around()`` 函数，然后回到 Python 代码标签页（现在应该看不到刚才定义的函数了），并用刚刚定义好的函数写一段小程序，以确保它们能正确工作。如果不能正确工作，请返回并修正。记得要在主程序里使用 ``from library import turn_right, turn_around`` 。

.. hint::

   定义好两个库函，然后使用下面的程序进行测试：

   .. code-block:: python
   
       from library import turn_right, turn_around
       move()
       turn_around()
       move()
       turn_right()
       move()
       turn_around()
       move()
       turn_left()  # 应该回到初始位置并且朝向和开始时一致


从现在开始，每当你要定义一个会被使用很多次的函数时，就把它放进库里，而不是每次都重新定义。


乐跑懂中文
---------------------------------

有一个特殊的库使乐跑能懂中文。比如，用 ``前进()`` 代替 ``move()``，乐跑也能明白。试试下面这段程序：

.. code-block:: python

    from reeborg_cn import 前进, 左转

    前进()
    左转()

.. topic:: 轮到你了！

    使用中文库（“reeborg_cn”）里的函数，写一段小程序。

.. admonition:: 写给想使用其它语言版本的教育者的内容

    在乐跑的世界右上方的语言菜单里，可以选择使用完全法语（界面和编程都用法语）。也可能存在由志愿者贡献的其它语言版本……或许你能成为一名志愿者并贡献你所翻译的版本！ ;-)
