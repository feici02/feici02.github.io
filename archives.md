---
layout: page
title: Archives
permalink: /archives/
---

<section>
{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  <h3>{{ year.name }}</h3>
    <ul>
      {% for post in year.items %}
        <li><a href="{{ post.url }}">{{ post.title }}</a>
          <span class="date">{{ post.date | date: "%B %-d, %Y" }}</span>
        </li>
      {% endfor %}
    </ul>
{% endfor %}
</section>
