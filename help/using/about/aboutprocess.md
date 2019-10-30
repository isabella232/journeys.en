---
title: User process
seo-title: User process
description: User process
seo-description: 
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: n
internal: n
snippet: y
---

# User process{#concept_y4b_4qt_52b}

Here are the main steps to configure and use this feature:

1. Configuring the event: this configuration is mandatory and performed by a **technical user**. You define the information expected and how to process it. Se[Configuring an event](../event/event.md#concept_gfj_fqt_52b).
1. Configuring the data source: this step is performed by a **technical user**. It allows you to define a connection to a system to retrieve additional information that will be used in your journeys, for example in your conditions. This is not required if you only leverage data from the events in your journey. See [Configuring a data source](../datasource/ds.md#concept_s1s_dqt_52b).
1. Configuring a custom action: this step is performed by a **technical user**. If you're using a third-party system to send your messages, this is where you will configure its connection to Journeys. See [Configuring a custom action](../custom-action/custom.md).
1. Creating and defining the journey: this is performed by a **business user**. This is where you create, define and publish your scenarios. See [Building a journey](../building-journeys/journey.md#concept_gq5_sqt_52b).
1. Testing and publishing the journey: this is performed by a **business user**. This validates and activates the journey. See [Testing and publishing the journey](../building-journeys/journeypublication.md#concept_mtc_lrt_52b).
1. Analyzing the journey via the dedicated reporting tools. This is performed by a **business user**. See [Building your Journeys reports](reporting.md#concept_rfj_wpt_52b).

Here is a schema of an end-to-end scenario:

![](../assets/journeydiagram.png) 
