---
layout: archive
title: "Case Studies"
permalink: /case-studies/
author_profile: true
---

Five projects tracing one arc: setting the data strategy, building the infrastructure it depends on, and getting the result to the people who act on it — leadership and customer success, not just a dashboard.

<div class="case-study-grid">
{% assign sorted_studies = site.case_studies | sort: "order" %}
{% for study in sorted_studies %}
<div class="case-study-card">
  <h3><a href="{{ study.url | relative_url }}">{{ study.title }}</a></h3>
  <p>{{ study.excerpt }}</p>
</div>
{% endfor %}
</div>