---
title: Sharing journey steps with Platform
description: Sharing journey steps with Platform
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# Sharing journey steps with Platform{#sharing-journey-steps}

This feature automatically creates schemas and streams datasets to Adobe Experience Platform for each step of an individual in a journey. This data can then be used for analysis via a business intelligence tool.

It is activated automatically for all customers.

The following schemas are created:

* Journey Step Profile Event schema for Journey Orchestration – Experience Events for steps taken in a Journey along with an Identity Map to be used for mapping to an individual Journey Participant.
* Journey Step Event schema for Journey Orchestration – Journey step event that is tied to a Journey Metadata.
* Journey schema with Journey Fields for Journey Orchestration – Journey Metadata to describe Journeys.

The following datasets are passed:

* Journey Step Profile Event schema for Journey Orchestration
* Journey Step Events
* Journeys

A specific list of fields is sent to Adobe Data Platform from Journey Orchestration. Common fields will be sent for every step that is processed in a journey. More specific fields are used for custom actions and enrichments.

The lists of fields are detailed here:

* journeySteps events common fields

* journeyStep events action execution fields

* journeyStep events data fetch fields

* journeyStep event identity fields

* journey fields




Some of those fields are only present in specific processing patterns (action execution, data fetch, ...). We want to limit the size of events, not to put any useless info contextually.