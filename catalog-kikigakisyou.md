---
layout: page
title: 聞書抄
toc:
- 陀思妥耶夫斯基小說衍生 
- 其他 

---

<div>writing while reading</div>

<div class="toc">

  {% assign collection_kikigakisyou = site.collections | where: "label", "kikigakisyou" | first %}
  {% assign categories = collection_kikigakisyou.category %}

			{% for category in categories %}
        <h3 id="{{ category }}"> {{ category }} </h3>
          <ul class="texts">
            {% assign posts_reverse = site.kikigakisyou | where: "category", category | sort | reverse %}
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
