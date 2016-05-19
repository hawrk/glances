:orphan:

glances
=======

SYNOPSIS
--------

**glances** [OPTIONS]

描述
-----------

**glances** is a cross-platform curses-based monitoring tool which aims
to present a maximum of information in a minimum of space, ideally to
fit in a classical 80x24 terminal or higher to have additional
information. It can adapt dynamically the displayed information
depending on the terminal size. It can also work in client/server mode.
Remote monitoring could be done via terminal or web interface.

**glances** is written in Python and uses the *psutil* library to get
information from your system.

选项
-------

.. include:: cmds.rst

例子
--------

监控本地机器 (standalone模式):

    $ glances

Monitor local machine with the web interface (Web UI):

    $ glances -w

Monitor local machine and export stats to a CSV file:

    $ glances --export-csv

Monitor local machine and export stats to a InfluxDB server with 5s
refresh time:

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
