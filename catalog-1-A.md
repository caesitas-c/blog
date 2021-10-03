---
layout: page
title: 分区A
toc:
- 原生示例
- 卷一 

---

<div>请浏览，或者点击左侧边栏中的主题跳动至目标。同一主题的文章以时间顺序排列。</div>

<div class="toc">

  {% assign collection_A = site.collections | where: "label", "A" | first %}
  {% assign categories = collection_A.category %}

			{% for category in categories %}
        <h3 id="{{ category }}"> {{ category }} </h3>
          <ul class="texts">
            {% assign posts_reverse = site.A | where: "category", category | sort | reverse %}
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
          </ul> 
      {% endfor %}

</div>