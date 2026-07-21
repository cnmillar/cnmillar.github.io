---
layout: single
title: "Designing and Building Data Systems"
permalink: /
author_profile: true
---

<div class="trend-demo">
  <p class="trend-demo__caption">Try it: the same logic behind <a href="/case-studies/warehouse-to-hubspot/">Getting Warehouse Data into the Hands That Need It</a>. Numbers below are illustrative, not real publisher data.</p>
  <div class="trend-demo__inputs">
    <label>
      Last week revenue
      <input type="range" id="prior-rev" min="1000" max="20000" step="100" value="8000" oninput="updateTrend()">
      <span id="prior-rev-val">$8,000</span>
    </label>
    <label>
      This week revenue
      <input type="range" id="current-rev" min="1000" max="20000" step="100" value="8000" oninput="updateTrend()">
      <span id="current-rev-val">$8,000</span>
    </label>
  </div>
  <div class="trend-demo__result">
    <span id="trend-status" class="trend-demo__status">Stable</span>
    <span id="trend-pct" class="trend-demo__pct"></span>
  </div>
</div>

<script>
function updateTrend() {
  const prior = parseFloat(document.getElementById('prior-rev').value);
  const current = parseFloat(document.getElementById('current-rev').value);
  document.getElementById('prior-rev-val').textContent = '$' + prior.toLocaleString();
  document.getElementById('current-rev-val').textContent = '$' + current.toLocaleString();

  const change = (current - prior) / prior;
  const statusEl = document.getElementById('trend-status');
  const pctEl = document.getElementById('trend-pct');
  let status, color;
  if (change > 0.05) { status = 'Growing'; color = '#0f6e3f'; }
  else if (change < -0.05) { status = 'Declining'; color = '#a32d2d'; }
  else { status = 'Stable'; color = '#555'; }

  statusEl.textContent = status;
  statusEl.style.color = color;
  pctEl.textContent = (change >= 0 ? '+' : '') + (change * 100).toFixed(1) + '% week over week';
}
</script>

I spent over six years as co-founder and COO of Indiegraf, building it into a publishing and revenue engine for 180+ independent news publishers across North and Latin America. I'm now transitioning into a Strategic Advisor role focused on data strategy, while continuing to serve on Indiegraf's Board. That shift is intentional: I'm moving toward the work I find most valuable, designing the systems that let organizations understand their customers, predict risk and grow with better information.

My background sits at an intersection that's genuinely rare: founder and executive experience, a business strategy lens, and hands-on technical ability to build the data infrastructure and models that make strategy real. I'm not trying to be a full-time engineer or a pure data scientist. I'm the person who can design the data function for a company *and* build it to actually run.

**What I do:**
- Set data and analytics strategy at the executive level — priorities, tradeoffs, and what a business actually needs to measure
- Tie technical work directly to business outcomes — revenue, retention, growth — so a model or pipeline serves a real decision, not just a technical exercise
- Data architecture and warehouse design (BigQuery, dbt, Fivetran, Airbyte)
- Designing pipelines and integrations that keep systems in sync automatically
- Turning data into something non-technical teams actually use — in the CRM, the inbox, or wherever they already work, not a dashboard they have to remember to check

Take a look at my [case studies](/case-studies/) to see this in practice, or email me at [hello@caitlinhavlak.com](mailto:hello@caitlinhavlak.com)