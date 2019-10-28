---
title: setHours
seo-title: setHours
description: setHours
seo-description: Learn about the function setHours
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

# setHours {#setHours}

Sets the hours of a date time or date time only. For example, if you want to wait until a certain hour tomorrow, you can force the hour.

## Category

Date

## Function syntax

`setHours(<parameter>)`

## Parameters

* dateTime
* dateTimeOnly
* integer

## Signatures and return type

`setHours(<dateTime>,<integer>)`

Returns a datetime.

`setHours(<dateTimeOnly>,<integer>)`

Returns a datetime without considering timezone.

## Examples

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns 2010-12-12T04:11:00Z.
