Java程序内存分析jmap
================

打印出某个java进程（使用pid）内存内的，所有‘对象’的情况（如：产生那些对象，及其数量）。

可以输出所有内存中对象的工具，甚至可以将VM 中的heap，以二进制输出成文本。使用方法 jmap -histo pid。如果连用SHELL jmap -histo pid>a.log可以将其保存到文本中去，在一段时间后，使用文本对比工具，可以对比出GC回收了哪些对象。jmap -dump:format=b,file=outfile 3024可以将3024进程的内存heap输出出来到outfile文件里，再配合MAT（内存分析工具(Memory Analysis Tool）或与jhat (Java Heap Analysis Tool)一起使用，能够以图像的形式直观的展示当前内存是否有问题。

64位机上使用需要使用如下方式：

	jmap -J-d64 -heap pid

命令格式
--------

    jmap [ option ] pid
	jmap [ option ] executable core
	jmap [ option ] [server-id@]remote-hostname-or-IP

参数说明
--------

* option：

	executable Java executable from which the core dump was produced.

	(可能是产生core dump的java可执行程序)

	core 将被打印信息的core dump文件

	remote-hostname-or-IP 远程debug服务的主机名或ip

	server-id 唯一id,假如一台主机上多个远程debug服务 

* 基本参数：

	-dump:[live,]format=b,file=<filename> 使用hprof二进制形式,输出jvm的heap内容到文件=. live子选项是可选的，假如指定live选项,那么只输出活的对象到文件. 

	-finalizerinfo 打印正等候回收的对象的信息.

	-heap 打印heap的概要信息，GC使用的算法，heap的配置及wise heap的使用情况.

	-histo[:live] 打印每个class的实例数目,内存占用,类全名信息. VM的内部类名字开头会加上前缀”*”. 如果live子参数加上后,只统计活的对象数量. 

	-permstat 打印classload和jvm heap长久层的信息. 包含每个classloader的名字,活泼性,地址,父classloader和加载的class数量. 另外,内部String的数量和占用内存数也会打印出来. 

	-F 强迫.在pid没有相应的时候使用-dump或者-histo参数. 在这个模式下,live子参数无效. 

	-h | -help 打印辅助信息 

	-J 传递参数给jmap启动的jvm. 




pid 需要被打印配相信息的java进程id

![img](http://static.oschina.net/uploads/space/2014/0701/171430_5oNu_1767531.png)

首先查看javaw的进程号，7712

![img](http://static.oschina.net/uploads/space/2014/0701/171945_MyQ9_1767531.png)

jmap -histo pid 展示class的内存情况

展示的信息为编号，实例数，字节，类名

![img](http://static.oschina.net/uploads/space/2014/0701/172257_kgad_1767531.png)

jmap -heap pid 展示pid的整体堆信息

![img](http://static.oschina.net/uploads/space/2014/0701/172458_KVFk_1767531.png)

说明如下：

		 Heap Configuration:#堆内存初始化配置
		 MinHeapFreeRatio = 40  #-XX:MinHeapFreeRatio设置JVM堆最小空闲比率  
		 MaxHeapFreeRatio = 70  #-XX:MaxHeapFreeRatio设置JVM堆最大空闲比率 
		 MaxHeapSize      = 268435456(256.0)#-XX:MaxHeapSize=设置JVM堆的最大大小
		 NewSize          = 1048576 (1.0MB) #-XX:NewSize=设置JVM堆的‘新生代’的默认大小 
		 MaxNewSize       = 4294901760 (4095.9375MB) #-XX:MaxNewSize=设置JVM堆的‘新生代’的最大大小 
		 OldSize          = 4194304 (4.0MB) #-XX:OldSize=设置JVM堆的‘老生代’的大小  
		 NewRatio         = 2 #-XX:NewRatio=:‘新生代’和‘老生代’的大小比率
		 SurvivorRatio    = 8 #-XX:SurvivorRatio=设置年轻代中Eden区与Survivor区的大小比值  
		 PermSize         = 12582912 (12.0MB) #-XX:PermSize=<value>:设置JVM堆的‘永生代’的初始大小 
		 MaxPermSize      = 67108864 (64.0MB) #-XX:MaxPermSize=<value>:设置JVM堆的‘永生代’的最大大小
		 Heap Usage:  
		 PS Young Generation 
		 Eden Space:#Eden区内存分布  
		    capacity = 71630848 (68.3125MB)
		    used     = 4272376 (4.074455261230469MB)
		    free     = 67358472 (64.23804473876953MB)
		    5.964435881032708% used
		 From Space:#其中一个Survivor区的内存分布
		 	capacity = 8912896 (8.5MB)
		 	used     = 0 (0.0MB)
		 	free     = 8912896 (8.5MB)
		 	0.0% used
		 To Space:#另一个Survivor区的内存分布
		 	capacity = 8912896 (8.5MB)
		 	used     = 0 (0.0MB)
		 	free     = 8912896 (8.5MB)
		 	0.0% used
		 PS Perm Generation#当前的 “永生代” 内存分布
			capacity = 59506688 (56.75MB)
			used     = 59312368 (56.56468200683594MB)
			free     = 194320 (0.1853179931640625MB)
			99.67344847019548% used

jmap -dump

![img](http://static.oschina.net/uploads/space/2014/0701/173507_SPFm_1767531.png)

导出的bin文件可以提供mat工具进行分析。接下来会讲jmap和mat如何进行内存分析。







