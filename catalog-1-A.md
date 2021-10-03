---
layout: page
title: 分区A
toc:
- 原生示例
- 卷一 
- 卷二
- 卷三
---

<div>请浏览，或者点击下拉菜单跳动至目标主题。同一主题的文章以时间顺序排列。</div>

<div class="toc">
  {% assign categories = site.categories | sort %}
			{% for category in categories %}
			{% assign name =  category | first  %}
      <h3 id="{{ name }}"> {{ name }} </h3>
      <ul class="texts">
        {% for posts in category %}
        {% assign posts_reverse =  posts | reverse  %}
				{% for post in posts_reverse %}
				{% if post.url != Nil %}
        <li class="text-title">
          <a href="{{ post.url | prepend: site.baseurl }}">
            {{ post.title }} 
          </a>
          <span class="rating">{{ post.rating }}</span>
        </li>
				{% endif %}
        {% endfor %} 
        {% endfor %}
      </ul> 
      {% endfor %}
  </div>