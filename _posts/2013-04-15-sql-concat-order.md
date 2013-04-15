---
layout: post
title: "oracle分析函数结合wm_concat实现排序后分组"
description: ""
category: blog
tags: [oracle, concat, 分析函数]
---
下午帮hli写了个sql。
wm_concat很好用，但是排序比较麻烦。

hli是这样的情景：
A给B发送数据，B处理。
B给A回复处理结果。
如果B回复的结果是失败，那么A需要重发消息。
如果A发送了已处理成功的数据，那么B会回复已处理过。
现需要将每组数据的发送过程、回复结果等等统计出来。

感谢funnsy提供的[解决方案](http://blog.csdn.net/funnsy/article/details/7479946):  
<pre>
<code>
select m, max(r)
from (select m, wm_concat(n) over (partition by m order by n) r from t)
group by m ;
</code>
</pre>

我照葫芦画瓢写了一个：  
<pre>
<code>
{% highlight sql %}
select  ves,voy,bln, max(r) as message
from (select  t.ves,t.voy, t.bln,wmsys.wm_concat(t.response_code||'~'||t.response_text||'~'||t.mtime) over (partition by t.ves,t.voy,t.bln order by t.mtime) r from v_ccre_info t where t.bln is not null)
group by ves,voy,bln
{% endhighlight %}
</code>
</pre>

看来Oracle的分析函数确实比较好用。
