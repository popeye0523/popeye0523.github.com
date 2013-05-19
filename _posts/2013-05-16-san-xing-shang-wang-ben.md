---
layout: post
title: "三星上网本SAMSUNG NC110p更改启动项改装XP"
description: ""
category: blog
tags: [SAMSUNG, 三星, NC110P]
---
{% include JB/setup %}

三星上网本NC110p，果然很奇葩。

首先按照正常思维去装，找不到U盘或者光驱启动项。开机按esc不管用，开机F2进bios，boot里面priority也只有硬盘HDD一项，泪奔。

不甘心，将BIOS设置一一仔细看了一遍，发现Advanced菜单下有个fast bios，是不明选项，于是勾选掉，插上U盘和外接光驱，启动顺序里面就出现了USB和光盘启动项。 

另外，三星官网不提供xp显卡驱动 只有win7驱动，手工生成一个！

生成驱动包的方法见这个帖子[Intel_GMA3600 XP显卡驱动安装方法（图）](http://hi.baidu.com/tbqs2916/item/8e2eb910a9995d5e2a3e228d)

剩下的就是装齐驱动开始XP之旅了。
