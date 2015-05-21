node-agent
=============
这个程序要实现哪些功能：

* 文件上传服务器，可以支持并发上传大文件
* 解压上传的压缩包到指定的目录，并自动创建软链
* 部署目录前和后分别执行制定的shell脚本
* 自动安装/升级/卸载一个软件包
* 定时向中心服务器汇报当期机器安装/运行的软件及版本号
* 定时收集机器的运行信息，基于linux的/proc文件系统进行分析，并发送到中心服务器

运行服务器程序
----
修改上传文件的根目录，和允许的最大尺寸。
```php
//设置上传文件的存储目录
$svr->setRootPath('/tmp/');
//设置允许上传的文件最大尺寸
$svr->setMaxSize(100*1024*1024);
```

在命令行中运行
```shell
php server.php
```

向服务器发送文件
----

```shell
php client.php -h 127.0.0.1 -p 9507 -f your_file.tar.gz
```
