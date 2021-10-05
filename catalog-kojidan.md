---
layout: page
title: 古事談
toc:
- 墓
- 其他

---

<div>中國歷史相關。</div>

<div class="toc">

  {% assign collection_kojidan = site.collections | where: "label", "kojidan" | first %}
  {% assign categories = collection_kojidan.category %}

			{% for category in categories %}
        <h3 id="{{ category }}"> {{ category }} </h3>
          <ul class="texts">
            {% assign posts_reverse = site.kojidan | where: "category", category | sort | reverse %}
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
