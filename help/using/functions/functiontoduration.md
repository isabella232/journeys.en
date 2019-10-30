---
title: toDuration
seo-title: toDuration
description: toDuration
seo-description: Learn about the function toDuration
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

# toDuration {#toDuration}

Converts an argument value to a duration.

## Category

Conversion

## Function syntax

`toDuration(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string|formats based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours|
|integer|number of milliseconds (epoch milliseconds)|

## Signatures and return type

`toDuration(<string>)`
`toDuration(<integer>)`

Returns a duration.

## Examples

`toDuration("PT10H")`

Returns duration of 10 hours.

`toDuration("PT4S")`

Returns duration of 4s.

`toDuration(4000)`

Returns duration of 4s.
