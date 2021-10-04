---
layout: page
title: 鏡華錄
toc: 鏡華錄一
- 

---

<div>請瀏覽，或者點擊左側邊欄中的主題跳動至目標。同一主題的文章以時間順序排列。</div>

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
