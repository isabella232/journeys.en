---
title: replace
seo-title: replace
description: replace
seo-description: Learn about the function replace
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

# replace {#replace}

Replaces the first occurrence of the source string by the target string in the base string.

## Category

String

## Function syntax

`replace(<parameters>)`

## Parameters

| Parameter | Type         |
|-----------|--------------|
| base      | string       |
| source    | string       |
| target    | string       |

## Signature and return type

`replace(baseString,sourceString,targetString)`

`replace(<string>,<string>,<string>)`
Return a string.

## Example

`replace("Hello World", "l", "x")`

Returns "Hexlo World".
