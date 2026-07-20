---
title: "Designing a Revenue Intelligence Engine"
excerpt: "A data strategy capstone on consolidating scattered data sources into a system built for retention, expansion, and partnership scaling."
---

## The problem

Indiegraf's data lived scattered across Stripe, Cakemail, AdButler, GA4, and HubSpot, each holding a piece of the picture. No single view existed of publisher health or revenue opportunity, which meant decisions about retention and growth were being made on partial information.

## The framing

Four strategic use cases anchored the design:

- **Retention** — identifying publishers at risk of churn early enough to intervene
- **Expansion** — identifying publishers ready for additional services
- **Partnership scaling** — supporting enterprise publisher networks with the reporting they need
- **Analytics products** — a path toward insights products publishers could use directly

## The architecture

A consolidated warehouse (BigQuery) as the single source of truth, with each source system feeding in rather than being queried separately. Fivetran and Airbyte handled most of the standard integrations. For APIs neither supported, custom pipelines were built using Google Cloud Functions, so no data source was left out of the picture just because a managed connector didn't exist for it. The goal was one place to answer questions about publisher health, not five.

## Tools

BigQuery as the central warehouse. Fivetran and Airbyte for source-system integration (Stripe, Chargebee, HubSpot). Custom pipelines on Google Cloud Functions for sources without managed connector support. Streamlit for the reporting and analytics layer.

## Why it mattered strategically

Before this, Indiegraf had no unified view of publisher health. Questions about who was at risk, who was ready to grow, and where the network needed attention were answered with scattered exports and manual pulls, not a system. Centralizing this data gave the business its first real intelligence layer on its own customer base: a foundation for retention, expansion, and partnership decisions that were previously made on incomplete information.

This is internal infrastructure, not a publisher-facing product yet. But it's the layer that would need to exist before any publisher-facing analytics product could be built on top of it.

## What this demonstrates

Designing the data function for a company, not just building one model inside it. The strategic use cases came first; the architecture was built to serve them, not the other way around.

This architecture is also what made it possible to get outcome data directly into the hands of the team that uses it daily — see [Getting Warehouse Data into the Hands That Need It](/case-studies/warehouse-to-hubspot/) for how that played out.