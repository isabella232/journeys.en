---
title: Constants
seo-title: Constants
description: Constants
seo-description: Learn about constants in advanced conditions
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

# Constants {#concept_gp3_rj5_dgb}

Technically, a constant always contains a data type. In the literal expression, we only specify the value. The data type can be inferred from the value (for example string, integer, decimal, etc.). For specific cases such as time zones, we use dedicated functions for the representation: _toTimeZone("Europe/Paris")_.

Here is how constant expressions are represented:

|Data Type|Description|Literal Representation |Example|
|-----|-----------------------------------------------------|----------------------------|----|
|string|Common sequence of characters.<br/>It doesn't have any specific size except the implicit one that comes from the environment such as the amount of memory available.<br/>JSON format: String<br/>Serialization format: UTF-8|`"<value>"`<br/>`'<value>'`|`"hello world"`<br/> `'hello world'`|
|integer|Integer value from -2^63 to 2^63-1.<br/>JSON format: Number|`<integer value>`|42|
|decimal|Decimal number.<br/> It represents a floating value:<br/>largest positive finite value of type double, (2-2^-52)x2^1023<br/>smallest positive normal value of type double, 2-1022<br/>smallest positive nonzero value of type double, 2 p-1074J<br/>SON format: Number<br/>Serialization format: using '.' as the decimal separator.|`<integer value>.<integer value>`|`3.14`|
|boolean|Boolean value written lowercase: true or false<br/>JSON format: Boolean|`true` <br/>`false`|`true`|
|dateTimeOnly|It represents a date-time without a time-zone, often viewed as year-month-day-hour-minute-second-millisecond.<br/>It does not store or represent a time-zone. <br/>Instead, it is a description of the date, as used for birthdays, combined with the local time as seen on a wall clock. <br/>It cannot represent an instant on the time-line without additional information such as an offset or time-zone.<br/>Serialization format: ISO-8601 extended offset date-time format.<br/> It uses DateTimeFormatter.ISO_LOCAL_DATE_TIME to deserialize and serialize the value.<br/> [Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME)).|`toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")`<br/>`toDateTimeOnly(<year>, <month>, <day>, <hour>, <minute>, <second>)`|`toDateTimeOnly("1977-04-22T06:00:00")`<br/>`toDateTimeOnly(1977, 4, 22, 6, 0, 0")`<br/>Examples of serialized dateTimeOnly:<br/>`2011-12-03T15:15:30`<br/>`2011-12-03T15:15:30.123`|
|dateTime|Date time constant that also considers time zone.<br/>It represents a date-time with an offset from UTC. It can be viewed as an instant in time with the additional information of the offset. <br/>It is a way to represent a specific “moment” at a certain place of the world.<br/>JSON format: String. It must be encapsulated in a toDateTime function.<br/>Serialization format: ISO-8601 extended offset date-time format. It uses DateTimeFormatter.ISO_OFFSET_DATE_TIME to deserialize and serialize the value. <br/>[Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME). You can also pass an integer passing an epoch value. <br/>[Read more](https://www.epochconverter.com/).<br/>Timezone can be specified by an offset or a timezone code (example: Europe/Paris, Z - meaning UTC).|`toDateTime("<dateTime in ISO-8601 format>")`<br/>`toDateTime(<integer value of an epoch in milliseconds>)`|toDateTime("1977-04-22T06:00:00Z")<br/>toDateTime("2011-12-03T15:15:30Z")<br/>toDateTime("2011-12-03T15:15:30.123Z")<br/>toDateTime("2011-12-03T15:15:30.123+02:00")<br/>toDateTime("2011-12-03T15:15:30.123-00:20")<br/> toDateTime(1560762190189)|
|timeZone|Id of a time zone using the java implementation such as "Europe/Paris".<br/>JSON format: String.<br/> It must be encapsulated in a TimeZone function.<br/>Serialization format: to deserialize a time zone ID, it uses the java function java.time.ZoneId.of. <br/>[Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/ZoneId.html#of-java.lang.String-).|`toTimeZone("<time zone id>"`)|toTimeZone("Europe/Paris")|
|duration|It represents a time-based amount of time, such as '34.5 seconds'.<br/> It models a quantity or amount of time in terms of milliseconds.<br/>The supported temporal units are:milliseconds,seconds,minutes, hours, days with one day equals to 24 hours.<br/> Years and months are not supported since they're not a fixed amount of time.<br/> JSON format: String. It must be encapsulated in a toDuration function.<br/>Serialization format: To deserialize a time zone ID, it uses the java function java.time.<br/>Duration.parse: the formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours.[Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-).|`toDuration("<duration in ISO-8601 format>")`<br/>`toDuration(<duration in milliseconds>)`|`toDuration("PT5S") // 5 seconds`<br/>`toDuration(500) // 500mstoDuration("PT20.345S")`<br/>` -- parses as "20.345 seconds"`<br/>`toDuration("PT15M")`<br/>` -- parses as "15 minutes" `<br/>`(where a minute is 60 seconds)`<br/>`toDuration("PT10H")`<br/>`-- parses as "10 hours" `<br/>`(where an hour is 3600 seconds)`<br/>`toDuration("P2D")`<br/>`-- parses as "2 days"`<br/>` (where a day is 24 hours or 86400 seconds)`<br/>`toDuration("P2DT3H4M")`<br/>`-- parses as "2 days, 3 hours and 4 minutes"`<br/>`toDuration("P-6H3M")`<br/>`-- parses as "-6 hours and +3 minutes"`<br/>`toDuration("-P6H3M")`<br/>`-- parses as "-6 hours and -3 minutes"`<br/>`toDuration("-P-6H+3M")`<br/>`-- parses as "+6 hours and -3 minutes"`|
|list|Comma separated list of expressions using square brackets as delimiters. <br/>Polymorphism is not supported, hence all the expressions contained in the list should have the same type.|`[<expression>, <expression>, ... ]`|`["value1","value2"]`<br/>`[3,5]`<br/>`[toDuration(500),toDuration(800)]`|
