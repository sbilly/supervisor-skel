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
	│  └─supervisor-initscripts
	└─src

- conf/supervisor/default

	对应部署后的系统目录 /etc/default 。

- conf/supervisor/supervisor

	必须修改 `supervisor.conf` 文件中的 `[inet_http_server]` 的 username 和 password 。参考文档：[http://supervisord.org/configuration.html#inet-http-server-section-settings](http://supervisord.org/configuration.html#inet-http-server-section-settings)。
	
	对应部署后的系统目录 /etc/supervisor 。`supervisor.conf` 可以在 `echo_supervisord_conf` 输出的基础上修改得到。

- misc/supervisor-initscripts/ubuntu

	以 submodule 的方式增加了 https://github.com/Supervisor/initscripts
 
	如果是 pip 安装的 supervisord 需要：

		ln -s /etc/supervisor/supervisord.conf /etc/supervisord.conf
		ln -s /usr/local/bin/supervisord /usr/bin/supervisord
		ln -s /usr/local/bin/supervisorctl /usr/bin/supervisorctl
		mkdir -p /var/log/supervisor/

	部署中需要将对应的启动脚本部署到系统目录，例如：/etc/init.d/supervisor

	来自于 [https://github.com/Supervisor/initscripts/blob/master/ubuntu](https://github.com/Supervisor/initscripts/blob/master/ubuntu)