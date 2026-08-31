---
title: "Bringing Publisher Data Into One Place"
excerpt: "Consolidating scattered publisher data into a single system built for retention, expansion, and partnership decisions."
order: 1
header:
  teaser: /assets/images/architecture-diagram-generic.svg
---

## The problem

Indiegraf's data lived scattered across several different systems — a CRM, a billing platform, an email platform, an ad platform, and web analytics — each holding a piece of the picture. No single view existed of publisher health or revenue opportunity, which meant decisions about retention and growth were being made on partial information.

## The framing

Four strategic use cases anchored the design:

- **Retention** — identifying publishers at risk of churn early enough to intervene
- **Expansion** — identifying publishers ready for additional services
- **Partnership scaling** — supporting enterprise publisher networks with the reporting they need
- **Analytics products** — a path toward insights products publishers could use directly

## The architecture

A consolidated warehouse as the single source of truth, with each source system feeding in rather than being queried separately. Most integrations were handled by managed connectors. For the systems that weren't supported, custom pipelines were built by hand, so no data source was left out of the picture just because an off-the-shelf option didn't exist for it.

One problem had to be solved before any of this could work: publishers didn't share a common identifier across systems, so the same publisher could look like several different, disconnected records depending on which tool you were looking at. Solving that meant designing a canonical publisher ID that every source system could be matched against, so a health score, a revenue number, and a support ticket all clearly point back to the same publisher rather than three separate ones. The goal was one place to answer questions about publisher health, not five.

## Tools

BigQuery as the central warehouse. Fivetran and Airbyte for most source-system integration. Custom pipelines on Google Cloud Functions for the systems those tools didn't support. A dbt model for the canonical publisher ID. Streamlit for the reporting and analytics layer.

<img src="/assets/images/architecture-diagram-generic.svg" alt="Bringing publisher data into one place" style="max-width:100%;display:block;margin:2rem auto;">

## Why it mattered strategically

Before this, Indiegraf had no unified view of publisher health. Questions about who was at risk, who was ready to grow, and where the network needed attention were answered with scattered exports and manual pulls, not a system. Centralizing this data gave the business its first real intelligence layer on its own customer base: a foundation for retention, expansion, and partnership decisions that were previously made on incomplete information.

This is internal infrastructure, not a publisher-facing product yet. But it's the layer that would need to exist before any publisher-facing analytics product could be built on top of it.

## What this demonstrates

Designing the data function for a company, not just building one model inside it. The strategic use cases came first; the architecture was built to serve them, not the other way around.

This architecture is also what made it possible to get outcome data directly into the hands of the team that uses it daily — see [Getting Data into the Hands That Need It](/case_studies/warehouse-to-hubspot/) for how that played out.