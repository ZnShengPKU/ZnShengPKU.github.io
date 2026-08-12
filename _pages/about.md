---
permalink: /
title: "About Me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

Hi, I’m Zinan Sheng(盛子楠), an undergraduate at Peking University. I work with Prof. Ge Li on data synthesis for large language models.

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

{% comment %}
  One list, newest first. Preprint versus published is carried by the venue
  badge — outlined for preprints, filled for published — so a second heading
  would only repeat what the badge already says.
{% endcomment %}
{% if site.publications.size > 0 %}
## Publications

<div class="pub-list">
  {% for post in site.publications reversed %}
    {% include publication-card.html post=post %}
  {% endfor %}
  {% include pub-equal-note.html posts=site.publications %}
</div>
{% endif %}
