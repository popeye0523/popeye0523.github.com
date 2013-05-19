---
layout: post
title: "ORACLE10g升级11g遇到的CLOB问题"
description: ""
category: blog
tags: [oracle, 升级, CLOB]
---
{% include JB/setup %}

### 问题描述
最近升级ORACLE，从10g升到11g，碰到一个WMSYS.WM_CONCAT函数版本差异的问题。

oracle的WMSYS.WM_CONCAT函数在Oracle Database 10g Enterprise Edition Release 10.2.0.4.0 - 64bi版本中的结果是一个字符型的数据，而在Oracle Database 11g Enterprise Edition Release 11.2 - 64bi版本中是一个CLOB类型。

这样，由于在sql中,若查询了LOB字段是不能使用distinct，union，和group by、max等关键字的，导致数据库报错。  
报错信息为：ORA-00932:数据类型不一致:应为 -，但却获得CLOB。


### 当时想的两个解决方法

临时解决方案：
在WMSYS.WM_CONCAT嵌套一层to_char()暂时过渡，但如果WMSYS.WM_CONCAT的结果长度超出2000，很有可能导致程序报错。

后续跟进：
重写一个与WMSYS.WM_CONCAT功能相同的函数，防止超长报错。
