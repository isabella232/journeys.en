---
title: matchRegExp
seo-title: matchRegExp
description: matchRegExp
seo-description: Learn about the function matchRegExp
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

# matchRegExp {#matchRegExp}

Returns true if the string in the first parameter matches the regular expression in the second parameter.For more information, see[this page](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Category

String

## Function syntax

`matchRegExp(<parameters>)`

## Parameters

|Parameter|Type|
|--- |--- |
|string|string|
|regexp|string|

## Signature and return type

`matchRegExp(<string>,<string>)`

Returns a true.

## Example

`matchRegExp("Hello World", "Hello\s+World")`

Returns true.

Explanation: here you check if the string satisfies the regular expression (java syntax): starts with "Hello", then any kind of string and finishes with "World".
