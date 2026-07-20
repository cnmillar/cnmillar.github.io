---
title: "Predicting Publisher Churn"
excerpt: "A Random Forest model to identify at-risk publisher accounts before they churn, built as part of a Data Science certificate capstone."
---

## The problem

Indiegraf serves 180+ independent publishers on a subscription model. Losing a publisher is costly, and without a system to flag risk early, the pattern only becomes visible after it's too late to act.

## Approach

- **Data:** account-level usage and behavioral signals collected across the publisher base
- **Model:** Random Forest, chosen for its ability to handle mixed feature types and surface which signals matter most, without requiring heavy feature engineering upfront
- **Scope:** 250 publisher accounts

## Tools

Python, pandas, scikit-learn for modeling and evaluation. Feature exploration and validation in Jupyter notebooks.

## Result

- **AUC: 0.81** — in plain terms, given one at-risk account and one healthy account, the model correctly ranks the at-risk one higher about 81% of the time
- Behavioral signals (engagement patterns, usage trends) were the strongest predictors, stronger than firmographic data like publisher size or tenure
- Data quality gaps capped accuracy further. That's a finding on its own: it points to specific gaps worth closing before the next iteration, not just a limitation to note in passing

## What this demonstrates

Going from a business problem to a working, evaluated model. Not the algorithm choice on its own, but the judgment behind what to build, what data to trust, and what the result actually means for the business.