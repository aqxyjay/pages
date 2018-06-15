---
layout: page
title: 学习总结
---

<ul class="posts">
  {% for post in site.posts %}
    {% if post.categories contains 'study' %}
        <li itemscope>
          <a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
          <p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%Y年%-m月%-d日" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>
        </li>
    {% endif %}
  {% endfor %}
</ul>