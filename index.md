---
layout: default
title: 首页
---


<div class="archive">
  <div class="timeline" id="timeline">
    {% assign posts_by_year = site.posts | group_by_exp:"post", "post.date | date: '%Y' " %}
    {% for group in posts_by_year %}
      <div class="archive-title">
        <h4 class="archive-year">{{ group.name }}</h4>
      </div>

      <ul>
      {% for post in group.items %}
        <li><div style="width:4rem;float:left;">{{ post.date | date: "%-m.%-d" }}</div> <a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" class="archive-item-link" title="{{post.title}}">{{ post.title }}</a></li>
      {% endfor %}
      </ul>

    {% endfor %}
  </div>
</div>