---
title: getBestSendTime
description: Learn about the function getBestSendTime
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

# getBestSendTime {#getBestSendTime}

Provides a predictive time of the best time for delivering an email to an individual.  To use this function, a [namespace](../event/eventnamespace.md) is needed.

## Category

Adobe Experience Platform

## Function syntax

`getBestSendTime(&lt;parameters>)`

## Parameters

|Parameter|Description|Type|
|--- |--- |--- |
|hours from current time|Number of hours to consider from the current time (max : 168)|`<integer>`|
|interaction type|"open" or "click"|`<string>`|
|default time in hours to wait|in case the predictive send time scores are not available|`<integer>`|

## Signature and returned type

`getBestSendTime(&lt;integer>,&lt;string>,&lt;integer>)`

Returns a datetime.

## Example

getBestSendTime(12,"open",8)
