# supervisor-skel

用 supervisord 实现远程服务管理的工具

## 文件夹结构

	supervisor-skel
	├─conf
	│  └─supervisor
	│      ├─default
	│      └─supervisor
	│          └─conf.d
	├─doc
	├─misc
	│  └─ubuntu-init
	└─src

- conf/supervisor/default

	对应部署后的系统目录 /etc/default 。

- conf/supervisor/supervisor

	必须修改 `supervisor.conf` 文件中的 `[inet_http_server]` 的 username 和 password 。参考文档：[http://supervisord.org/configuration.html#inet-http-server-section-settings](http://supervisord.org/configuration.html#inet-http-server-section-settings)。
	
	对应部署后的系统目录 /etc/supervisor 。`supervisor.conf` 可以在 `echo_supervisord_conf` 输出的基础上修改得到。

- misc/ubuntu-init/supervisor
 
	对应部署后的系统目录 /etc/init.d/supervisor

	来自于 [https://github.com/Supervisor/initscripts/blob/master/ubuntu](https://github.com/Supervisor/initscripts/blob/master/ubuntu)