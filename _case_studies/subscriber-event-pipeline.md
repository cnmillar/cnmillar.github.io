---
title: "Multi-Tenant Subscriber Event Pipeline"
excerpt: "An event-driven system that routes subscription changes across multiple publisher sites to the right downstream tools in real time — segmentation, fulfillment alerts, and audit logging included."
order: 5
---

## The problem

A single subscription platform serving several independent publisher sites means every subscription event needs to land in the right place: the right email list, the right audience segment, sometimes a fulfillment team, always a record for later analysis. A daily batch job can't make those real-time distinctions, and treating every event the same regardless of which publisher or plan it belongs to loses information that matters downstream.

## Approach

A webhook receives subscription events (new, renewed, canceled) as they happen and routes each one based on which publisher site it belongs to. From there:

- The subscriber is created or updated in the correct publisher's email platform account, tagged by publication and plan so segmentation stays accurate without manual list management
- Subscriptions tied to home delivery trigger a separate notification to the fulfillment team with the delivery details needed to act on it
- New subscriptions trigger a real-time Slack notification to the team
- Every event is logged to BigQuery, raw and parsed, so the data is available for reporting later, not just acted on and discarded
- Errors are caught and routed to a dedicated alert channel, so failures get noticed immediately rather than surfacing as a mystery gap in the data days later

## Tools

Google Cloud Functions (HTTP-triggered), Cloud Secret Manager for credentials, BigQuery for event logging, Cakemail API for subscriber and segmentation management, Slack for real-time and error notifications.

## Result

Subscription events across multiple publisher sites are handled correctly and immediately, with no manual reconciliation step and no event lost to a batch window. The BigQuery log turns every webhook event into a durable, queryable record, which is what makes it possible to build reporting or troubleshoot a data discrepancy after the fact.

## What this demonstrates

Multi-tenant systems design: recognizing that "route this event" isn't one decision but several (which account, which segment, does this need a fulfillment alert, does this need to be logged for later), and building a single pipeline that makes all of those distinctions correctly and automatically.