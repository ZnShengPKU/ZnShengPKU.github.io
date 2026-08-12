---
permalink: /
title: "About Me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

Hi, I’m Zinan Sheng(盛子楠), an undergraduate at Peking University. I work with Prof. Ge Li on large language models, focusing on model architecture, training methods, and data synthesis.

## News

- **Aug 2026** — One [paper](/publication/2026-10-12-ase-llm-feature-implementation) accepted to **ASE 2026** (to appear).

{% if site.data.education.size > 0 %}
## Education

<div class="xp-list">
  {% for entry in site.data.education %}
    {% include experience-card.html entry=entry %}
  {% endfor %}
</div>
{% endif %}

{% if site.data.experience.size > 0 %}
## Experience

<div class="xp-list">
  {% for entry in site.data.experience reversed %}
    {% include experience-card.html entry=entry %}
  {% endfor %}
</div>
{% endif %}

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
