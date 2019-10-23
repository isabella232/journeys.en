---
title: toDateTime
seo-title: toDateTime
description: toDateTime
seo-description: Learn about the function toDateTime
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
# toDateTime {#toDateTime}

Converts an argument value into a date time value, depending on its type.

## Category

Conversion

## Function syntax

`toDateTime(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| deserialized dateTime | string |
| timezone | string |
| dateTimeOnly | dateTimeOnly|
| Year | integer |
| Month | integer |
| Day of month | integer |
| Hour | integer |
| Minute | integer |
| Second | integer |

Timezone id must be a string constant. It cannot be a field reference nor an expression.

## Signatures and return types

`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default timezone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`
`toDateTime(<integer>)`
`toDateTime(<timeZone>,<integer>)`

Return a datetime.

## Examples

`toDateTime ("2016-08-18T23:17:59.123Z")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.
