.. _rabbitmq:

RabbitMQ
========

你可以将统计信息导出到``RabbitMQ``服务器上 (AMQP Broker)。应该像下面这样在Glances配置文件中定义连接：

.. code-block:: ini

    [rabbitmq]
    host=localhost
    port=5672
    user=glances
    password=glances
    queue=glances_queue

然后这样运行Glances：

.. code-block:: console

    $ glances --export-rabbitmq
