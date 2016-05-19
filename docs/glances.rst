:orphan:

glances
=======

SYNOPSIS
--------

**glances** [OPTIONS]

描述
-----------

**glances**是一个基于curses的跨平台监控工具，旨在在最小的空间上展示最多的信息，较为理想地适用于经典的80x24或更高的终端，以拥有额外信息。根据终端大小，它可以动态地适应展示信息。它还可以工作在client/server模式下。通过终端和web界面，可以进行远程监控。

**glances**使用Python写的，使用*psutil*库来获取你的系统的信息。

选项
-------

.. include:: cmds.rst

例子
--------

监控本地机器 (standalone模式):

    $ glances

使用web界面监控本地机器 (Web UI):

    $ glances -w

监控本地机器并将统计信息导出到一个CSV文件中：

    $ glances --export-csv

监控本地机器并以5s的刷新时间将统计信息导出到一个InfluxDB服务器：

    $ glances -t 5 --export-influxdb

启动一个Glances服务器 (server模式):

    $ glances -s

连接Glances到一个Glances服务器 (client模式):

    $ glances -c <ip_server>

连接到一个Glances服务器并导出统计信息到一个StatsD服务器上：

    $ glances -c <ip_server> --export-statsd

启动client浏览器 (browser模式):

    $ glances --browser

作者
------

Nicolas Hennion aka Nicolargo <contact@nicolargo.com>
