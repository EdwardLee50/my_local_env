# 概述

1. 这是一个用于快速搭建本地开发环境的docker-compose文件，前提是安装好docker 和 docker-compose。

2. config为配置文件，可以修改里面的内容，然后运行docker-compose up -d命令，即可快速搭建本地开发环境。在启动前，需修改 config/rocketmq/single/broker.conf 文件中的 brokerIP1，具体可见其中注释

3. 启动后，各web页面如下，其中{{your_ip}}指具体承接docker运行时的ip地址，可以是本机、虚拟机内网ip、阿里云ecs的ip等，记得放开相关端口：

3.1. phpadmin: http://{{your_ip}}:8081

3.2. redis-commander: http://{{your_ip}}:8082

3.3. xxl-job-admin: http://{{your_ip}}:8083/xxl-job-admin

3.4. rocketmq-dashboard: http://{{your_ip}}:8084

3.5. kibana: http://{{your_ip}}:5601

其中需要注意的是，xxl-job-admin需要依赖于基础数据，可通过在phpadmin中执行 ./config/xxl-job/tables_xxl_job.sql 进行初始化，其中也包含了初始账号密码，账号：admin，密码：123456