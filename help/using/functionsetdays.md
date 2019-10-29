---
title: setDays
seo-title: setDays
description: setDays
seo-description: Learn about the function setDays
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

# setDays {#setDays}

Sets the day of a date time or date time only. For example, if you want to wait until a certain day of the month, you can force the day.

## Category

Date

## Function syntax

`setDays(<parameter>)`

## Parameters

|Parameter|Type|
|--- |--- |
|dateTime||
|dateTimeOnly||
|days|integer|

## Signatures and return type

`setDays(<dateTime>,<integer>)`

Returns a datetime.

`setDays(<dateTimeOnly>,<integer>)`

Returns a datetime without considering timezone.

## Examples

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Returns 2010-12-25T01:11:00Z.
