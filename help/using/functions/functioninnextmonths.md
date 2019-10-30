---
title: inNextMonths
seo-title: inNextMonths
description: inNextMonths
seo-description: Learn about the function inNextMonths
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

# inNextMonths {#inNextMonths}

Function defining if a given date or dateTime is between now and now + delta months.

## Category

Date

## Function syntax

`inNextMonths(<parameter>)`

## Parameters

* dateTime
* integer

## Signatures and return type

`inNextMonths(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns true.
