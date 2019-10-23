---
title: random
seo-title: random
description: random
seo-description: Learn about the function random
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: y
internal: n
snippet: y
---

# random {#random}

Generates a random number between 0 and 1.

## Category

Maths

## Function syntax

`random(<parameters>)`

## Signature and return type

`random()`
Returns a decimal.

## Example

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explanation: if the success ratio has no value/is null, the default value will be applied and will be a random figure between 0 and 1 * 100 (meaning 0 to 100).
