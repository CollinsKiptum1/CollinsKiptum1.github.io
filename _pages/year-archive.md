---
title: "📚 Posts from 2023–2025"
permalink: /posts/
layout: default
author_profile: true
---

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% assign filtered_years = postsByYear | where_exp:"year", "year.name >= '2023' and year.name <= '2025'" %}

<h2>📅 Posts from 2023–2025</h2>
{% for year in filtered_years %}
  <h3>📆 {{ year.name }} ({{ year.items | size }} posts)</h3>
  <ul>
    {% for post in year.items %}
      <li>
        📝 <strong>{{ post.date | date: "%b %d" }}</strong> —
        <a href="{{ post.url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
