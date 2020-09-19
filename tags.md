---
layout: page
title: "标签"
description: "根据标签查看"  
header-img: "img/semantic.jpg"  
---

### 所有标签
--------------------
<div id='tag_cloud'>
{% for tag in site.tags %}
 <a style="color:#000000" href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}"><img src="/img/标签.png" />{{ tag[0] }}&nbsp;&nbsp;</a>
{% endfor %}
</div>

### 详细
--------------------
<ul class="listing">
{% for tag in site.tags %}
  <b class="listing-seperator" id="{{ tag[0] }}">#{{ tag[0] }}</b>

 
{% for post in tag[1] %}
  <li class="listing-item">
  <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
{% endfor %}
</ul>

<script src="/media/js/jquery.tagcloud.js" type="text/javascript" charset="utf-8"></script> 
<script language="javascript">
$.fn.tag_cloud.defaults = {
    size: {start: 1, end: 1, unit: 'em'},
      color: {start: '#f8e0e6', end: '#ff3333'}
};

$(function () {
    $('#tag_cloud a').tagcloud();
});
</script>
