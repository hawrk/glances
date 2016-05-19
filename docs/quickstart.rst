.. _quickstart:

快速入门
==========

本页面提供给了一个关于如何使用Glances的一个很好的介绍。
Glances提供3种模式：

- Standalone
- Client/Server
- Web server

Standalone模式
---------------

只需运行：

.. code-block:: console

    $ glances

Client/Server模式
------------------

如果你想从一个名为``client``的机器上远程监控一台名为``server``的机器，只需在该服务器上运行：

.. code-block:: console

    server$ glances -s

在该客户端上运行：

.. code-block:: console

    client$ glances -c @server

其中，``@server``是该服务器的IP地址或主机名。

使用``--browser``选项，Glances可以集中可用的Glances服务器。通过配置文件（``[serverlist]``部分），可以静态定义该服务器列表。

在server模式下，你可以使用``-B ADDRESS``设置绑定地址，使用``-p PORT``设置监听TCP端口。

在client模式下，你可以用``-p PORT``设置该服务器的TCP端口。

默认的绑定地址是``0.0.0.0`` (Glances将会在所有可用的网络端口上监听)，默认的TCP端口是``61209``。

在client/server模式下，限制由服务器侧设置。

你可以设置访问服务器的密码 ``--password``。默认情况下，用户名是``glances``，但是你可以使用``--username``来改变它。

如果你要求，SHA密码将存储在``username.pwd``文件中。

Glances兼容``IPv6``。只需使用``-B ::``选项来绑定所有的IPv6地址。

Autodiscover
^^^^^^^^^^^^

通过``zeroconf``协议，Glances还可以检测和展示在你的网络中所有可用的Glances服务器 (Windows上不可用):

.. code-block:: console

    client$ glances --browser

使用``--disable-autodiscover``以禁用它。

SNMP
^^^^

作为一个实验性功能，如果客户端没有检测到Glances服务器，那么后者将试图使用``SNMP``协议抓取统计信息：

.. code-block:: console

    client$ glances -c @snmpserver

.. 注意::
    通过SNMP请求抓取的统计信息是有限的，并且与操作系统有关。

Web Server模式
---------------

.. image:: _static/screenshot-web.png

如果你想从任何带有web浏览器的设备上远程监控一台名为``server``的机器，只需带``-w``选项运行服务器：

.. code-block:: console

    server$ glances -w

然后在客户端上自己喜欢的Web浏览器中输入以下网址：

::

    http://@server:61208

其中，``@server``是该服务器的IP地址或主机名。

要修改页面的刷新速度，只需在URL的末尾添加以秒为单位的周期。例如，要每隔``10``秒刷新页面：

::

    http://@server:61208/10

Glances web界面遵循自适应网页设计原则。

下面是在Android上的Chrome截图：

.. image:: _static/screenshot-web2.png
