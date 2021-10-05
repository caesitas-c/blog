---
layout: page
title: 鏡華錄
toc:
- 平安至室町
- 安土桃山
- 幕末明治
- 大正昭和
- 平成及以後

---

<div>我流日系小美人學。</div>

<div class="toc">

  {% assign collection_kaleidoscope = site.collections | where: "label", "kaleidoscope" | first %}
  {% assign categories = collection_kaleidoscope.category %}

			{% for category in categories %}
        <h3 id="{{ category }}"> {{ category }} </h3>
          <ul class="texts">
            {% assign posts_reverse = site.kaleidoscope | where: "category", category | sort | reverse %}
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
