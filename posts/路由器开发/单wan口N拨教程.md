单wan口N拨教程
--------------


安装macvlan及Multiwan的软件包
===============
进入System-SoftWare-页面 点一下Update

然后查找macvlan点左边的install 

然后查找Multiwan点左边的install 

然后查找Multiwan-app点左边的install 

查看你的wan口的端口名
=====================
使用SecureCRT软件登陆

root@OpenWrt:~# `cat /etc/config/network`

你将看到如下内容

	config 'switch' 'eth0' 
	option 'enable' '1' 
	config 'switch_vlan' 'eth0_0' 
	option 'device' 'eth0' 
	option 'vlan' '0'  
	option 'ports' '1 2 3 4 5' #port1、2、3、4和cpu5属于vlan 0 
	config 'switch_vlan' 'eth0_1' #记住这里的eth0_1后面有用即是可用来拨号的LAN口
	option 'device' 'eth0' 
	option 'vlan' '1'  
	option 'ports' '0 5' #port0和cpu 5属于vlan 1 


编辑/etc/rc.local 增加虚拟wan口
=============

root@OpenWrt:~# `vi /etc/rc.local`

按键盘I进入修改模式

	sleep 6
	ip link add link eth0.1 ethl1 type macvlan #增加wan2虚拟网卡eth0.1对应前面记下的
	ifconfig ethl1 hw ether 00:11:22:33:44:1E 
	ifconfig ethl1 up 

	ip link add link eth0.1 ethl2 type macvlan #增加wan2虚拟网卡eth0.1对应前面记下的
	ifconfig ethl2 hw ether 00:11:22:33:44:2E 
	ifconfig ethl2 up 

编辑/etc/config/network 添加wan口拨号
==================


	config 'interface' 'wan'  
	option 'ifname' 'eth0.1' 
	option 'proto' 'pppoe'  
	option 'password' '用户名' 
	option 'username' '密码' 
	option 'defaultroute' '1' 
	option 'peerdns' '1' 

	config 'interface' 'wan2'  
	option 'ifname' 'ethl1'  #对应前面添加的虚拟口
	option 'defaultroute' '0'  
	option 'peerdns' '0' 
	option 'proto' 'none' 




参考
=============

[OpenWrt单wan口N拨教程](http://wenku.baidu.com/link?url=SIQEqVqd6xzi9ntkP65v14W0VsGKI10ifYnclXGQNgeKqSUEQbyLjr_ClovFYuzj0TXPilGc-KCkL_0QZEuhBLJDhOIzKnwKSHdCgU8LyUa###)





  


 
