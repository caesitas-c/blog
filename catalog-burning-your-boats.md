---
layout: page
title: 焚舟紀
toc:
- 國設短篇
- 普設短篇
- 睡美人
- 柳樹園下
- 活劇
- 杜松子酒與金髮藍眼

---

<div>Hetalia England/America.</div>

<div class="toc">

  {% assign collection_burning-your-boats = site.collections | where: "label", "burning-your-boats" | first %}
  {% assign categories = collection_burning-your-boats.category %}

			{% for category in categories %}
        <h3 id="{{ category }}"> {{ category }} </h3>
          <ul class="texts">
            {% assign posts_reverse = site.burning-your-boats | where: "category", category | sort | reverse %}
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
