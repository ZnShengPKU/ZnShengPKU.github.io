---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

👋Hi, I'm Zinan Sheng, currently undergraduate at Peking University, School of EECS.<br> 
I am currently researching **LLMs/MLLMs architecture and learning algorithm** under the supervision of Prof. Ge Li.

{% assign preprints = site.publications | where: "category", "preprints" %}
{% assign publications = site.publications | where_exp: "item", "item.category != 'preprints'" %}

{% if preprints.size > 0 %}
## Preprints

<ul>
  {% for post in preprints reversed %}
    <li style="margin-bottom: 1.5rem;">
      <strong>{{ post.title }}</strong><br>
      {{ post.authors | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines }}<br>
      In <i>{{ post.venue }}</i> {{ post.date | date: "%Y" }}. 
      {% if post.paperurl %}[<a href="{{ post.paperurl }}">Download paper</a>]{% endif %}
      {% if post.codeurl %}[<a href="{{ post.codeurl }}">code</a>]{% endif %}
    </li>
  {% endfor %}
</ul>
{% endif %}

{% if publications.size > 0 %}
## Publications

<ul>
  {% for post in publications reversed %}
    <li style="margin-bottom: 1.5rem;">
      <strong>{{ post.title }}</strong><br>
      {{ post.authors | markdownify | remove: '<p>' | remove: '</p>' | strip_newlines }}<br>
      In <i>{{ post.venue }}</i> {{ post.date | date: "%Y" }}. 
      {% if post.paperurl %}[<a href="{{ post.paperurl }}">Download paper</a>]{% endif %}
      {% if post.codeurl %}[<a href="{{ post.codeurl }}">code</a>]{% endif %}
    </li>
  {% endfor %}
</ul>
{% endif %}
