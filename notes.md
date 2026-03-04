---
layout: default
title: Technical Notes
permalink: /notes/
---

# Technical Notes

<ul>
  {% comment %} 
    1. 全ページからパスに 'technologies/' を含むものを抽出
    2. 日付(date)順に並べ替え
    3. 逆順(新しい順)にする
  {% endcomment %}
  
  {% assign tech_pages = site.pages | where_exp: "item", "item.path contains 'technologies/'" | sort: 'date' | reverse %}

  {% for post in tech_pages %}
    <li>
      <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>