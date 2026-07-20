---
layout: archive
title: "Case Studies"
permalink: /case-studies/
author_profile: true
excerpt: "Five projects spanning data strategy, modeling, and the infrastructure that makes both usable."
---

Five projects spanning data strategy, modeling, and the infrastructure that makes both usable.

{% assign sorted_studies = site.case_studies | sort: "order" %}
{% for study in sorted_studies %}
  <div style="margin-bottom: 2em;">
    <h2><a href="{{ study.url | relative_url }}">{{ study.title }}</a></h2>
    <p>{{ study.excerpt }}</p>
  </div>
{% endfor %}