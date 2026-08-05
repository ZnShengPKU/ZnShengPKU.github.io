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

<div class="pub-list">
  {% for post in preprints reversed %}
    {% include publication-card.html post=post %}
  {% endfor %}
</div>
{% endif %}

{% if publications.size > 0 %}
## Publications

<div class="pub-list">
  {% for post in publications reversed %}
    {% include publication-card.html post=post %}
  {% endfor %}
</div>
{% endif %}
