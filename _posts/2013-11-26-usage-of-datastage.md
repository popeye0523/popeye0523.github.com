---
layout: post
title: "关于使用datastage的记录"
description: ""
category: blog
tags: [datastage]
---
{% include JB/setup %}

### 首先说明一点，这个记录只是我自己学习导数用的，不算是一般范例，仅做参考。

生成建表sql语句

将java写的datastage项目导入eclipse

D:\Projects\Java\datastage\job\dbmodel

这个目录下面

要改两个文件：

DB_Model_HIS_CM.xls

每个项目一个excel文档，以CM为例。

里面主要描述CM项目的表结构、是否非空，主键等

增加或者修改完成后，跑一下excel中的subMakeSql_Total这个宏，C:\tablescripts目录下就会生成相应的建表sql脚本。

注意：
1、要把excel宏安全的设置打开 

2、需要在C盘创建一个C:\tablescripts目录 

3、宏报错或者不生效的时候，查看一下单元格的行列是否跟下图一致。 

![](/blog/image/datastage/1.png)


源数据供数增全量.xls 

这个excel要改两个sheet，一个是汇总，一个是CM。 

注意一下这两个sheet中增全量即可 


在项目中，以java application执行 

/datastage/src/com/datastage/StartMain.java 

> 
参数配置文件【SysConfig.properties】配置字典如下：

请选择批量生成作业代码还是单个生成：【B 批量生成/S 单个生成】！ 

> s 

> 请输入系统的数字代号： 
┏━━━━━━━━━┳━━━━━━━━━┳━━━━━━━━━━━━━━━━━┓
┃系统代号     ┃系统简称     ┃文件路径                                    
┣━━━━━━━━━╋━━━━━━━━━╋━━━━━━━━━━━━━━━━━┫
┃1                ┃CM             ┃./job/dbmodel/DB_Model_HIS_CM.xls     
┃2                ┃FA              ┃./job/dbmodel/DB_Model_HIS_FA.xls    
┃3                ┃SC              ┃./job/dbmodel/DB_Model_HIS_SC.xls    
┗━━━━━━━━━┻━━━━━━━━━┻━━━━━━━━━━━━━━━━━┛

> 1 

> 表作业ODS_CM_CUS_BASE已生成 

表作业ODS_CM_CUS_COM已生成 

表作业ODS_CM_CUS_INDIV已生成 

全部作业已完成 

本次一共生成3个job 

** 注：这个console是输出的简化，大概表示这个意思 

操作上，主要是选择批量和系统代号。 **

执行完成后，/datastage/job/XT/目录下面自动生成一个文件：ODS_CM.dsx 

这个/datastage/job/XT/ODS_CM.dsx也就是datastage的项目文件，等下导入到datastage中编译执行即可 

打开“Designer 客户机”和“Director 客户机” 

--designer客户机是用来创建、编译、执行项目工程的，如下图 

![](/blog/image/datastage/2.png) 

--director客户机是用来跟踪designer执行状态日志的，如下图 

![](/blog/image/datastage/3.png) 

填写datastage服务器的ip地址或者hosts文件中定义好的别名（我的hosts里面写的是：192.24.16.62 datastage），使用isadmin/isadmin登录，注意端口，如下图 

![](/blog/image/datastage/4.png) 


前面用java生成了一个文件，ODS_CM.dsx，现在就把它导入到datastage的作业中 

1、在designer中，选择Import --》datastage components 

![](/blog/image/datastage/5.png) 

2、选择import selected，来执行一个dsx的导入；如果要全部导入，选择import all 

![](/blog/image/datastage/6.png) 

3、开始导入进程，速度比较慢，需要耐心等一会。 

![](/blog/image/datastage/7.png) 

4、导入完成后，打开相应的job，开始编译。 

![](/blog/image/datastage/8.png) 

![](/blog/image/datastage/9.png) 

director中，能看到这几个job的状态变化。 

从 

![](/blog/image/datastage/10.png) 

变成了 

![](/blog/image/datastage/11.png) 

5、编译完成后，就可以运行了。 






