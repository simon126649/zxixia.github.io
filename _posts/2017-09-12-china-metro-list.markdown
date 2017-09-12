---
layout: post
title:  "中国城市地铁信息汇总"
categories: Favorite
tags: Metro
author: 西夏
description: 中国所有已开通地铁的城市信息汇总。
---



<table border="1" class="text-center">
  <tr bgcolor="#eaecf0">
  	<th width="160px" class="text-center">标识</th>
    <th width="50px" class="text-center">序号</th>
    <th width="150px" class="text-center">开通时间</th>
    <th width="150px" class="text-center">城市</th>
    <th width="150px" class="text-center">运营线路数</th>
    <th width="150px" class="text-center">通车里程</th>
    <th width="200px" class="text-center">官方网站</th>
  </tr>
  
	{% for metro in site.data.metros %}
		<tr height="80px">
	    <td bgcolor="#eaecf0">
	    	<img src="/assets/images/post/2017-09-12-china-metro-list/{{ metro.logo }}" {% if metro.imgWidth %} width="{{ metro.imgWidth }}" {% endif %}/>
	    </td>
	    <td>{{ forloop.index }}</td>
	    <td>{{ metro.year }}</td>
	    <td>{{ metro.city }}</td>
	    <td>{{ metro.line }}</td>
	    <td>{{ metro.miles }}公里</td>
	    <td><a href= "{{ metro.url }}">{{ metro.urlTitle }}</a></td>
	  </tr>
	{% endfor %}
    
</table>



<!-- 后面是文章参考资料 -->
<br/>
### 参考资料：

1，[维基百科-中国城市轨道交通系统][wiki-china-metro-list]

2，[地铁族-两岸四地城市轨道交通开通情况][ditiezu-pages]

3，[UrbanRail.net][urbanrail-net]

---

<!-- 文章插图和超链接 -->

[wiki-china-metro-list]: https://zh.wikipedia.org/wiki/%E4%B8%AD%E5%9B%BD%E5%9F%8E%E5%B8%82%E8%BD%A8%E9%81%93%E4%BA%A4%E9%80%9A%E7%B3%BB%E7%BB%9F
[ditiezu-pages]: http://www.ditiezu.com/thread-497320-1-1.html
[urbanrail-net]: http://www.urbanrail.net/
