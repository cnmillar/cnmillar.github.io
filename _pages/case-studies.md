---
layout: archive
title: "Case Studies"
permalink: /case-studies/
author_profile: true
---

{% for study in site.case_studies %}
  <div style="margin-bottom: 2em;">
    <h2><a href="{{ study.url | relative_url }}">{{ study.title }}</a></h2>
    <p>{{ study.excerpt }}</p>
  </div>
{% endfor %}
