---
title: inSegment
seo-title: inSegment
description: inSegment
seo-description: Learn about the function inSegment
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

# inSegment {#inSegment}

Checks if an individual belongs to a given segment.The segment name must be a string constant. It cannot be a field reference nor an expression.

## Category

Adobe Experience Platform

## Function syntax

`inSegment(<parameter>)`

## Parameters

|Parameter|Description|Type|
|--- |--- |--- |
|Constant|The segment name |`<string>`|

## Signature and returned type

`inSegment(<string>)`

Returns a boolean.

## Example

`inSegment("men over 50")`
