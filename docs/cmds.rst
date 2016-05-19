.. _cmds:

命令参考
=================

命令行选项
--------------------

.. option:: -h, --help

    显示帮助信息并退出

.. option:: -V, --version

    显示程序的版本号并退出

.. option:: -d, --debug

    启用debug模式

.. option:: -C CONF_FILE, --config CONF_FILE

    到配置文件的路径

.. option:: -3, --disable-quicklook

    禁用quick look模块

.. option:: -4, --full-quicklook

    禁用all but quick look and load

.. option:: --disable-cpu

    禁用CPU模块

.. option:: --disable-mem

    禁用memory模块

.. option:: --disable-swap

    禁用swap模块

.. option:: --disable-load

    禁用load模块

.. option:: --disable-network

    禁用network模块

.. option:: --disable-ip

    禁用IP模块

.. option:: --disable-diskio

    禁用disk I/O模块

.. option:: --disable-fs

    禁用filesystem模块

.. option:: --disable-folder

    禁用folder模块

.. option:: --disable-sensors

    禁用sensors模块

.. option:: --disable-hddtemp

    禁用HD temperature模块

.. option:: --disable-raid

    禁用RAID模块

.. option:: --disable-docker

    禁用Docker模块

.. option:: -5, --disable-top

    禁用top菜单 (QuickLook, CPU, MEM, SWAP 和 LOAD)

.. option:: -2, --disable-left-sidebar

    禁用network, disk I/O, FS和sensors模块 (需要py3sensors库)

.. option:: --disable-process

    禁用process模块

.. option:: --disable-log

    禁用log模块

.. option:: --disable-bold

    禁用终端bold模式

.. option:: --disable-bg

    禁用终端背景颜色

.. option:: --enable-process-extended

    启用extended stats on top process

.. option:: --enable-history

    启用history模式 (需要matplotlib库)

.. option:: --path-history PATH_HISTORY

    为graph history设置导出路径

.. option:: --export-csv EXPORT_CSV

    导出统计信息到一个CSV文件中

.. option:: --export-influxdb

    导出统计信息到一个InfluxDB服务器上 (需要influxdb库)

.. option:: --export-opentsdb

    导出统计信息到一个OpenTSDB服务器上 (需要potsdb库)

.. option:: --export-statsd

    导出统计信息到一个StatsD服务器上 (需要statsd库)

.. option:: --export-rabbitmq

    导出统计信息到RabbitMQ broker上 (需要pika库)

.. option:: --export-riemann

    导出统计信息到Riemann服务器上 (需要bernhard库)

.. option:: --export-elasticsearch

    导出统计信息到Elasticsearch服务器上 (需要elasticsearch库)

.. option:: -c CLIENT, --client CLIENT

    通过IPv4/IPv6地址或者主机名连接到一个Glances服务器

.. option:: -s, --server

    以server模式运行Glances

.. option:: --browser

    启动客户端浏览器 (服务器列表)

.. option:: --disable-autodiscover

    禁用autodiscover特性

.. option:: -p PORT, --port PORT

    定义 client/server TCP 端口 [默认：61209]

.. option:: -B BIND_ADDRESS, --bind BIND_ADDRESS

    绑定服务器到给定的IPv4/IPv6地址或主机名

.. option:: --username

    定义client/server 用户名

.. option:: --password

    定义client/server密码

.. option:: --snmp-community SNMP_COMMUNITY

    SNMP社区

.. option:: --snmp-port SNMP_PORT

    SNMP端口

.. option:: --snmp-version SNMP_VERSION

    SNMP版本 (1, 2c 或者 3)

.. option:: --snmp-user SNMP_USER

    SNMP用户名 (仅用于SNMPv3)

.. option:: --snmp-auth SNMP_AUTH

    SNMP 认证密钥 (仅用于SNMPv3)

.. option:: --snmp-force

    force SNMP mode

.. option:: -t TIME, --time TIME

    set refresh time in seconds [default: 3 sec]

.. option:: -w, --webserver

    run Glances in web server mode (bottle lib needed)

.. option:: -q, --quiet

    do not display the curses interface

.. option:: -f PROCESS_FILTER, --process-filter PROCESS_FILTER

    set the process filter pattern (regular expression)

.. option:: --process-short-name

    force short name for processes name

.. option:: -0, --disable-irix

    task's CPU usage will be divided by the total number of CPUs

.. option:: --hide-kernel-threads

    hide kernel threads in process list

.. option:: --tree

    display processes as a tree

.. option:: -b, --byte

    display network rate in byte per second

.. option:: --diskio-show-ramfs

    show RAM FS in the DiskIO plugin

.. option:: --diskio-iops

    show I/O per second in the DiskIO plugin

.. option:: --fahrenheit

    display temperature in Fahrenheit (default is Celsius)

.. option:: -1, --percpu

    start Glances in per CPU mode

.. option:: --fs-free-space

    display FS free space instead of used

.. option:: --theme-white

    optimize display colors for white background

交互式命令
--------------------

The following commands (key pressed) are supported while in Glances:

``ENTER``
    Set the process filter

    **Note**: on OS X, please use ``CTRL-H`` to delete
    filter.

    Filter is a regular expression pattern:

    - ``gnome``: matches all processes starting with the ``gnome``
      string

    - ``.*gnome.*``: matches all processes containing the ``gnome``
      string

``a``
    Sort process list automatically

    - If CPU ``>70%``, sort processes by CPU usage

    - If MEM ``>70%``, sort processes by MEM usage

    - If CPU iowait ``>60%``, sort processes by I/O read and write

``b``
    Switch between bit/s or Byte/s for network I/O

``B``
    View disk I/O counters per second

``c``
    根据CPU使用排列进程

``d``
    显示/隐藏 disk I/O统计信息

``D``
    启用/禁用Docker 统计信息

``e``
    启用/禁用top extended统计信息

``E``
    擦除当前进程过滤器

``f``
    显示/隐藏文件系统和文件夹监控统计信息

``F``
    Switch between file system used and free space

``g``
    为当前history生成图表

``h``
    显示/隐藏 the help screen

``i``
    根据I/O比率排列进程

``I``
    显示/隐藏 IP模块

``l``
    显示/隐藏 log messages

``m``
    根据MEM使用排列进程

``M``
    Reset processes summary min/max

``n``
    显示/隐藏 network stats

``p``
    根据名称排列进程

``q|ESC``
    退出当前Glances会话

``r``
    重置history

``R``
    显示/隐藏 RAID插件

``s``
    显示/隐藏 sensors统计信息

``t``
    根据CPU times (TIME+)排列进程

``T``
    View network I/O as combination

``u``
    根据USER排列进程

``U``
    View cumulative network I/O

``w``
    删除完成的warning日志消息

``x``
    删除完成的warning和critical日志信息

``z``
    显示/隐藏 processes统计信息

``0``
    启用/禁用Irix/Solaris模式

    Task's CPU usage will be divided by the total number of CPUs

``1``
    Switch between global CPU and per-CPU stats

``2``
    启用/禁用left sidebar

``3``
    启用/禁用the quick look模块

``4``
    启用/禁用all but quick look and load模块

``5``
    启用/禁用top菜单(QuickLook, CPU, MEM, SWAP和LOAD)

``/``
    Switch between process command line or command name

在Glances客户端浏览器 (通过``--browser``命令行参数可进入):

``ENTER``
    运行选择的服务器

``UP``
    Up in the servers list

``DOWN``
    Down in the servers list

``q|ESC``
    退出Glances
