# Redis Installation


Office Site: https://redis.io/download			


    #setp 1. make directory for redis
    >$ cd /opt
    opt>$ mkdir redis
    opt>$ cd redis

    #setp 2. download redis package 
    opt/redis>$ wget http://download.redis.io/releases/redis-5.0.3.tar.gz

    #setp 3. extract redis package 
    opt/redis>$ tar xzf redis-5.0.3.tar.gz

    #setp 4. compile redis
    opt/redis>$ cd  redis-5.0.3
    opt/redis/edis-5.0.3>$ make


    #setp 5.edit Redis config 
    opt/redis/edis-5.0.3>$ vi redis.conf


    #设置后台运行 
    daemonize yes 
    #设置log文件路径 
    logfile /opt/redis/redis-server.log 
    #设置访问密码 
    requirepass root 
    #设置访问规则为远程访问，注释掉bind配置 
    #bind 0.0.0.0


    #setp 5.Run Redis 
    opt/redis/redis-5.0.3>$ src/redis-server  /opt/redis/redis-5.0.3/redis.conf


Noted:
You can interact with Redis using the built-in client:

    $ src/redis-cli -a root
    redis> set foo bar 
    OK 
    redis> get foo 
    "bar"
