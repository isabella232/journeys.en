---
title: toString
seo-title: toString
description: toString
seo-description: Learn about the function toString
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

# toString {#toString}

Converts an argument value into a string value, depending on its type.

## Category

Conversion

## Function syntax

`toString(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|date|converts the date in UTC date format|
|dateTime|converts to ISO-8601 format|
|dateTimeOnly|converts to ISO-8601 format|
|duration|converts to ISO-8601 format|
|timezone|converts into the zone id|
|integer|converts to string representation of the value (1 becomes “1”)|
|decimal|converts to string representation of the value (1.5 becomes “1.5”)|
|boolean|converts the boolean value to a quoted value (true becomes “true”)|

## Signatures and return type

`toString(<dateTimeOnly>)`
`toString(<dateTime>)`
`toString(<duration>)`
`toString(<timeZone>)`
`toString(<string>)`
`toString(<boolean>)`
`toString(<integer>)`
`toString(<decimal>)`

Returns a string.

## Example

`toString(4)`

Returns "4".

