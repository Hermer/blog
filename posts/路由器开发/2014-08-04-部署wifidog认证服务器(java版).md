部署wifidog认证服务器(java版)
-----------------------------

1. 搭建硬件及网络环境
====================

* 需要普通路由器1个，刷了apfree固件的路由器一个，Windows电脑一台，网线若干，宽带网络。
* 按照下图的拓扑结构进行搭建。

  ![link](http://images.cnitblog.com/i/630372/201406/302150587774951.png)

2. 获取软件及工具并安装
=======================

* 获取并安装jdk6
* 获取并安装MySQL
* 安装MyEclipse
* 获取java版wifidog认证服务器源码(https://github.com/C-hill/java4wifidog_server)

3. 项目部署
===========

因为MyEclipse自带了Tomcat插件，所以直接用MyEclipse的Tomcat插件进行部署。

* 打开MyEclipse,导入源码,部署到Tomcat
* 配置Tomcat中server.xml文件(该步骤主要是为了实现wifidog的接口标准)

		<Host name="localhost" appBase="webapps" unpackWARs="true" autoDeploy="true" xmlValidation="false" xmlNamespaceAware="false"> 
    		<Context path="" docBase="部署路径(绝对路径或appBase的相对路径)" debug="0" reloadable="true"/> 
		</Host>

* 创建数据库并执行wifidog.sql脚本，配置db.properties文件。

4. 调试运行
===========

* 在浏览器中输入“localhost:8080”，出现接口测试页面如下图，则服务器部署成功

	![link](http://images.cnitblog.com/i/630372/201406/302152091219574.png)

* 路由器设置
	* 通过cmd查看电脑的ip地址。
	* 输入192.168.0.1进入路由器管理界面进行配置。
	* 配置认证服务器url为：电脑ip。
	* 配置服务器端口为：8080。
	* 开启wifidog。

* 验证wifidog是否有效，在浏览器打开任意网址，正常情况下都会跳转到认证登录页面,如下图
	
	![link](http://images.cnitblog.com/i/630372/201406/302153026374258.png)

	这里已经实现了用户名密码认证，接下来可以通过测试接口添加用户名密码，然后输入用户名密码即可上网。具体步骤如下：

	打开localhost:8080进入测试接口首页，进入user接口后，如下图可以看到增加用户的接口，需要参数“device_token”，该参数对应的是表“ap”中的字段“dev_md5”，所以可以到数据库中获取对应的“dev_md5”然后填入，参数“username”，“password”自行定义即可。

	添加完用户名密码后，即可通过在认证页面输入该用户名密码实现认证上网。

	![link](http://images.cnitblog.com/i/630372/201406/302153326376423.png)