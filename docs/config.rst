.. _config:

配置
=============

不是一定要配置文件才能使用Glances的。

此外，要访问更多设置，则需要一个配置文件。

位置
--------

你可以将``glances.conf``文件放在下面的位置上：

=========== ============================================================
``Linux``   ~/.config/glances, /etc/glances
``*BSD``    ~/.config/glances, /usr/local/etc/glances
``OS X``    ~/Library/Application Support/glances, /usr/local/etc/glances
``Windows`` %APPDATA%\glances
=========== ============================================================

在Windows XP上，``%APPDATA%``路径是：

::

    C:\Documents and Settings\<User>\Application Data

而Windows Vista和更新的版本：

::

    C:\Users\<User>\AppData\Roaming


用户指定的选项覆盖系统范围的选项，而命令行给出的选项覆盖前面两者。

语法
------

Glances以*ini*语法读取配置文件。

每个插件和导出模块可以有一个部分。下面是CPU插件的例子：

.. code-block:: ini

    [cpu]
    user_careful=50
    user_warning=70
    user_critical=90
    iowait_careful=50
    iowait_warning=70
    iowait_critical=90
    system_careful=50
    system_warning=70
    system_critical=90
    steal_careful=50
    steal_warning=70
    steal_critical=90

日志
-------

Glances将其所有内部信息记录到一个日志文件中。

使用命令行上的``-d``选项，可以记录``DEBUG``信息。

默认情况下，``glances.log``文件位于临时目录下：

===================== ==================================================
``Linux, *BSD, OS X`` /tmp
``Windows``           %APPDATA%\\Local\\temp
===================== ==================================================

假如``glances.log``不可写，那么将会创建一个新的文件，并将其返回给用户控制台。
