---
title: "Predicting Publisher Churn"
excerpt: "A model to identify at-risk publisher accounts before they churn, built as part of a Data Science certificate capstone."
order: 3
header:
  teaser: /assets/images/churn-model-diagram.svg
---

## The problem

Indiegraf serves 180+ independent publishers on a subscription model. Losing a publisher is costly, and without a system to flag risk early, the pattern only becomes visible after it's too late to act.

## The framing

The goal was to catch risk early using signals already being collected: how actively a publisher was using the platform, and how that activity was trending over time. Rather than waiting for a cancellation to reveal a problem, the model looks for the early warning signs that tend to show up beforehand.

## Tools

Python, pandas, and scikit-learn for modeling and evaluation, using a Random Forest model trained on 250 publisher accounts. Feature exploration and validation in Jupyter notebooks.

## Result

- **AUC: 0.81** — in plain terms, given one at-risk account and one healthy account, the model correctly ranks the at-risk one higher about 81% of the time
- Behavioral signals (engagement patterns, usage trends) were the strongest predictors, stronger than firmographic data like publisher size or tenure
- Data quality gaps capped accuracy further. That's a finding on its own: it points to specific gaps worth closing before the next iteration, not just a limitation to note in passing

## What this demonstrates

Going from a business problem to a working, evaluated model. Not the algorithm choice on its own, but the judgment behind what to build, what data to trust, and what the result actually means for the business.