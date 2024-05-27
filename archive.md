---
layout: page
title: Archive
permalink: /archive/
---

{% assign grouped_posts = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in grouped_posts %}
  <strong>{{ year.name }}</strong>
  <table>
    {% for post in year.items %}
    <tr>
      <td>{{ post.date | date: "%B %d" }}</td>
      <td><a href="..{{ post.url }}">{{ post.title }}</a></td>
      <td>{{ post.content | number_of_words }}</td>
    </tr>
    {% endfor %}
  </table>
{% endfor %}

{{ site.posts | size }}
