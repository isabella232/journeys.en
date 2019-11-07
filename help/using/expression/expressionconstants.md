---
title: Constants
description: Learn about constants in advanced conditions
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

<table>
    <tr>
        <td>Data Type</td>
        <td>Description</td>
        <td>Literal Representation</td>
        <td>Example</td>
    </tr>
    <tr>
        <td>string</td>
        <td><p>Common sequence of characters.</p><br /><p>It doesn't have any specific size except the implicit one that comes from the environment such as the amount of memory available.</p><br /><p>JSON format: String</p><br /><p>Serialization format: UTF-8</p></td>
        <td>"&lt;value&gt;"<br />'&lt;value&gt;'</td>
        <td>"hello world"<br /> 'hello world'</td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Integer value from -2^63 to 2^63-1.</p><br /><p>JSON format: Number</p></td>
        <td>&lt;integer value&gt;</td>
        <td>42</td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Decimal number.</p><br />It represents a floating value:<ul><li><br />largest positive finite value of type double, (2-2^-52)x2^1023</li><br /><li>smallest positive normal value of type double, 2-1022</li><br /><li>smallest positive nonzero value of type double, 2 p-1074</li></ul><br /><p>JSON format: Number</p><br /><p>Serialization format: using '.' as the decimal separator.</p></td>
        <td>&lt;integer value&gt;.&lt;integer value&gt;</td>
        <td>3.14</td>
    </tr>
    <tr>
        <td>boolean</td>
        <td>Boolean value written lowercase: true or false<br />JSON format: Boolean</td>
        <td>true
        <br />false</td>
        <td>true</td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>It represents a date-time without a time-zone, often viewed as year-month-day-hour-minute-second-millisecond.</p><br /><p>It does not store or represent a time-zone.</p><br /><p>Instead, it is a description of the date, as used for birthdays, combined with the local time as seen on a wall clock.</p><br /><p>It cannot represent an instant on the time-line without additional information such as an offset or time-zone.</p><br /><p>Serialization format: ISO-8601 extended offset date-time format.</p><br /><p>It uses DateTimeFormatter.ISO_LOCAL_DATE_TIME to deserialize and serialize the value.</p><br /> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Learn more</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly in ISO-8601 format&gt;")</p><br /><p>toDateTimeOnly(&lt;year&gt;, &lt;month&gt;, &lt;day&gt;, &lt;hour&gt;, &lt;minute&gt;, &lt;second&gt;)</p></td>
        <td><p>toDateTimeOnly("1977-04-22T06:00:00")</p><br /><p>toDateTimeOnly(1977, 4, 22, 6, 0, 0")</p><br /><p>Examples of serialized dateTimeOnly:</p><br /><p>2011-12-03T15:15:30</p><br /><p>2011-12-03T15:15:30.123</p></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td>Date time constant that also considers time zone.<br />It represents a date-time with an offset from UTC. It can be viewed as an instant in time with the additional information of the offset. <br />It is a way to represent a specific “moment” at a certain place of the world.<br />JSON format: String.&lt;/br&gt; It must be encapsulated in a toDateTime function.<br />Serialization format: ISO-8601 extended offset date-time format. It uses DateTimeFormatter.ISO_OFFSET_DATE_TIME to deserialize and serialize the value. <br /><a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Learn more</a>. You can also pass an integer passing an epoch value. <br /><a href="https://www.epochconverter.com/">Read more</a>.<br />Timezone can be specified by an offset or a timezone code (example: Europe/Paris, Z - meaning UTC).</td>
        <td>toDateTime("&lt;dateTime in ISO-8601 format&gt;")<br />toDateTime(&lt;integer value of an epoch in milliseconds&gt;)</td>
        <td>toDateTime("1977-04-22T06:00:00Z")<br />toDateTime("2011-12-03T15:15:30Z")<br />toDateTime("2011-12-03T15:15:30.123Z")<br />toDateTime("2011-12-03T15:15:30.123+02:00")<br />toDateTime("2011-12-03T15:15:30.123-00:20")<br /> toDateTime(1560762190189)</td>
    </tr>
    <tr>
        <td>timeZone</td>
        <td>Id of a time zone using the java implementation such as "Europe/Paris".<br />JSON format: String.<br /> It must be encapsulated in a TimeZone function.<br />Serialization format: to deserialize a time zone ID, it uses the java function java.time.ZoneId.of. <br /><a href="https://docs.oracle.com/javase/8/docs/api/java/time/ZoneId.html#of-java.lang.String-">Read more</a>.</td>
        <td>toTimeZone("&lt;time zone id&gt;")</td>
        <td>toTimeZone("Europe/Paris")</td>
    </tr>
    <tr>
        <td>duration</td>
        <td>It represents a time-based amount of time, such as '34.5 seconds'.<br /> It models a quantity or amount of time in terms of milliseconds.<br />The supported temporal units are:milliseconds,seconds,minutes, hours, days with one day equals to 24 hours.<br /> Years and months are not supported since they're not a fixed amount of time.<br /> JSON format: String. It must be encapsulated in a toDuration function.<br />Serialization format: To deserialize a time zone ID, it uses the java function java.time.<br />Duration.parse: the formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours.<a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Learn more</a>.</td>
        <td>toDuration("&lt;duration in ISO-8601 format&gt;")<br />toDuration(&lt;duration in milliseconds&gt;)</td>
        <td>toDuration("PT5S") // 5 seconds<br />toDuration(500) // 500mstoDuration("PT20.345S")<br /> -- parses as "20.345 seconds"<br />toDuration("PT15M")<br /> -- parses as "15 minutes" <br />(where a minute is 60 seconds)<br />toDuration("PT10H")<br />-- parses as "10 hours" <br />(where an hour is 3600 seconds)<br />toDuration("P2D")<br />-- parses as "2 days"<br /> (where a day is 24 hours or 86400 seconds)<br />toDuration("P2DT3H4M")<br />-- parses as "2 days, 3 hours and 4 minutes"<br />toDuration("P-6H3M")<br />-- parses as "-6 hours and +3 minutes"<br />toDuration("-P6H3M")<br />-- parses as "-6 hours and -3 minutes"<br />toDuration("-P-6H+3M")<br />-- parses as "+6 hours and -3 minutes"</td>
    </tr>
    <tr>
        <td>list</td>
        <td>Comma separated list of expressions using square brackets as delimiters. <br />Polymorphism is not supported, hence all the expressions contained in the list should have the same type.</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><code>["value1","value2"]</code><br /><code>[3,5]</code><br /><code>[toDuration(500),toDuration(800)]</code></td>
    </tr>
</table>
