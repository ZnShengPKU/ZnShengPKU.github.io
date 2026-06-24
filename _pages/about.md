---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Hi, I’m Zinan Sheng(盛子楠), an undergraduate at Peking University’s School of EECS, Class of 2029. I work with Prof. Ge Li on large language models, focusing on model architecture, training methods, and data synthesis.
I’m also a research intern at Unipat AI, where I explore data synthesis for coding.

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
