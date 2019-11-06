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

|Data Type|Description|Literal Representation|Example|
|-----|-------------|----------------|----|
|string|Common sequence of characters.<br/>It doesn't have any specific size except the implicit one that comes from the environment such as the amount of memory available.<br/>JSON format: String<br/>Serialization format: UTF-8|`"<value>"`<br/>`'<value>'`|`"hello world"`<br/> `'hello world'`|
|integer|Integer value from -2^63 to 2^63-1.<br/>JSON format: Number|`<integer value>`|42|
|decimal|Decimal number.<br/> It represents a floating value:<br/>largest positive finite value of type double, (2-2^-52)x2^1023<br/>smallest positive normal value of type double, 2-1022<br/>smallest positive nonzero value of type double, 2 p-1074J<br/>SON format: Number<br/>Serialization format: using '.' as the decimal separator.|`<integer value>.<integer value>`|`3.14`|
|boolean|Boolean value written lowercase: true or false<br/>JSON format: Boolean|`true` <br/>`false`|`true`|
|dateTimeOnly|It represents a date-time without a time-zone, often viewed as year-month-day-hour-minute-second-millisecond.<br/>It does not store or represent a time-zone. <br/>Instead, it is a description of the date, as used for birthdays, combined with the local time as seen on a wall clock. <br/>It cannot represent an instant on the time-line without additional information such as an offset or time-zone.<br/>Serialization format: ISO-8601 extended offset date-time format.<br/> It uses DateTimeFormatter.ISO_LOCAL_DATE_TIME to deserialize and serialize the value.<br/> [Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME)).|`toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")`<br/>`toDateTimeOnly(<year>, <month>, <day>, <hour>, <minute>, <second>)`|`toDateTimeOnly("1977-04-22T06:00:00")`<br/>`toDateTimeOnly(1977, 4, 22, 6, 0, 0")`<br/>Examples of serialized dateTimeOnly:<br/>`2011-12-03T15:15:30`<br/>`2011-12-03T15:15:30.123`|
|dateTime|Date time constant that also considers time zone.<br/>It represents a date-time with an offset from UTC. It can be viewed as an instant in time with the additional information of the offset. <br/>It is a way to represent a specific “moment” at a certain place of the world.<br/>JSON format: String.</br> It must be encapsulated in a toDateTime function.<br/>Serialization format: ISO-8601 extended offset date-time format. It uses DateTimeFormatter.ISO_OFFSET_DATE_TIME to deserialize and serialize the value. <br/>[Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME). You can also pass an integer passing an epoch value. <br/>[Read more](https://www.epochconverter.com/).<br/>Timezone can be specified by an offset or a timezone code (example: Europe/Paris, Z - meaning UTC).|`toDateTime("<dateTime in ISO-8601 format>")`<br/>`toDateTime(<integer value of an epoch in milliseconds>)`|toDateTime("1977-04-22T06:00:00Z")<br/>toDateTime("2011-12-03T15:15:30Z")<br/>toDateTime("2011-12-03T15:15:30.123Z")<br/>toDateTime("2011-12-03T15:15:30.123+02:00")<br/>toDateTime("2011-12-03T15:15:30.123-00:20")<br/> toDateTime(1560762190189)|
|timeZone|Id of a time zone using the java implementation such as "Europe/Paris".<br/>JSON format: String.<br/> It must be encapsulated in a TimeZone function.<br/>Serialization format: to deserialize a time zone ID, it uses the java function java.time.ZoneId.of. <br/>[Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/ZoneId.html#of-java.lang.String-).|`toTimeZone("<time zone id>"`)|toTimeZone("Europe/Paris")|
|duration|It represents a time-based amount of time, such as '34.5 seconds'.<br/> It models a quantity or amount of time in terms of milliseconds.<br/>The supported temporal units are:milliseconds,seconds,minutes, hours, days with one day equals to 24 hours.<br/> Years and months are not supported since they're not a fixed amount of time.<br/> JSON format: String. It must be encapsulated in a toDuration function.<br/>Serialization format: To deserialize a time zone ID, it uses the java function java.time.<br/>Duration.parse: the formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours.[Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-).|`toDuration("<duration in ISO-8601 format>")`<br/>`toDuration(<duration in milliseconds>)`|`toDuration("PT5S") // 5 seconds`<br/>`toDuration(500) // 500mstoDuration("PT20.345S")`<br/>` -- parses as "20.345 seconds"`<br/>`toDuration("PT15M")`<br/>` -- parses as "15 minutes" `<br/>`(where a minute is 60 seconds)`<br/>`toDuration("PT10H")`<br/>`-- parses as "10 hours" `<br/>`(where an hour is 3600 seconds)`<br/>`toDuration("P2D")`<br/>`-- parses as "2 days"`<br/>` (where a day is 24 hours or 86400 seconds)`<br/>`toDuration("P2DT3H4M")`<br/>`-- parses as "2 days, 3 hours and 4 minutes"`<br/>`toDuration("P-6H3M")`<br/>`-- parses as "-6 hours and +3 minutes"`<br/>`toDuration("-P6H3M")`<br/>`-- parses as "-6 hours and -3 minutes"`<br/>`toDuration("-P-6H+3M")`<br/>`-- parses as "+6 hours and -3 minutes"`|
|list|Comma separated list of expressions using square brackets as delimiters. <br/>Polymorphism is not supported, hence all the expressions contained in the list should have the same type.|`[<expression>, <expression>, ... ]`|`["value1","value2"]`<br/>`[3,5]`<br/>`[toDuration(500),toDuration(800)]`|



<table><thead class="thead">
    <tr>
        <th class="entry" id="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1">Data Type</th>
        <th class="entry" id="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2">Description</th>
        <th class="entry" id="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3">Literal Representation</th>
        <th class="entry" id="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4">Example</th>
    </tr>
</thead><tbody class="tbody">
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">string</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">Common sequence of characters. It doesn't have any specific size except the implicit one that comes from the environment such as the amount of memory available. </p>
            <p class="p">JSON format: String</p>
            <p class="p">Serialization format: UTF-8</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">"&lt;value&gt;" <p class="p"></p>'&lt;value&gt;'</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>"hello world"</code></pre>
            <pre class="pre codeblock"><code>'hello world'</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">integer</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">Integer value from -2^63 to 2^63-1.</p>
            <p class="p">JSON format: Number</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">&lt;integer value&gt;</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>42</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">decimal</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">Decimal number. It represents a floating value:</p>
            <ul class="ul" id="concept_gp3_rj5_dgb__ul_cr4_scq_c3b">
<li class="li">largest positive finite value of type double, (2-2^-52)x2^1023</li>
<li class="li">smallest positive normal value of type double, 2-1022</li>
<li class="li">smallest positive nonzero value of type double, 2 p-1074</li>
            </ul>
            <p class="p">JSON format: Number</p>
            <p class="p">Serialization format: using '.' as the decimal separator.</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">&lt;integer value&gt;.&lt;integer value&gt;</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>3.14</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">boolean</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">Boolean value written lowercase: true or false</p>
            <p class="p">JSON format: Boolean</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">true <p class="p"></p> false</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>true</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">dateTimeOnly</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">It represents a date-time without a time-zone, often viewed as year-month-day-hour-minute-second-millisecond.</p>
            <p class="p">It does not store or represent a time-zone. Instead, it is a description of the date, as used for birthdays, combined with the local time as seen on a wall clock. It cannot represent an instant on the time-line without additional information such as an offset or time-zone.</p>
            <p class="p">Serialization format: ISO-8601 extended offset date-time format. It uses DateTimeFormatter.ISO_LOCAL_DATE_TIME to deserialize and serialize the value. <a class="xref" href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME" target="_blank">Learn more</a>.</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">
            <p class="p">toDateTimeOnly("&lt;dateTimeOnly in ISO-8601 format&gt;")</p>
            <p class="p">toDateTimeOnly(&lt;year&gt;, &lt;month&gt;, &lt;day&gt;, &lt;hour&gt;, &lt;minute&gt;, &lt;second&gt;)</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>toDateTimeOnly("1977-04-22T06:00:00")</code></pre>
            <pre class="pre codeblock"><code>toDateTimeOnly(1977, 4, 22, 6, 0, 0")</code></pre>
            <p class="p">Examples of serialized dateTimeOnly:</p>
            <pre class="pre codeblock"><code>2011-12-03T15:15:30</code></pre>
            <pre class="pre codeblock"><code>2011-12-03T15:15:30.123</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">dateTime</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">Date time constant that also considers time zone.</p>
            <p class="p">It represents a date-time with an offset from UTC. It can be viewed as an instant in time with the additional information of the offset. It is a way to represent a specific “moment” at a certain place of the world. </p>
            <p class="p">JSON format: String. It must be encapsulated in a toDateTime function.</p>
            <p class="p">Serialization format: ISO-8601 extended offset date-time format. It uses DateTimeFormatter.ISO_OFFSET_DATE_TIME to deserialize and serialize the value. <a class="xref" href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME" target="_blank">Learn more</a>. You can also pass an integer passing an epoch value. <a class="xref" href="https://www.epochconverter.com/" target="_blank">Read mode</a>.</p>
            <p class="p">Timezone can be specified by an offset or a timezone code (example: Europe/Paris, Z - meaning UTC).</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">
            <p class="p">toDateTime("&lt;dateTime in ISO-8601 format&gt;")</p>
            <p class="p">toDateTime(&lt;integer value of an epoch in milliseconds&gt;)</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>toDateTime("1977-04-22T06:00:00Z")</code></pre>
            <pre class="pre codeblock"><code>toDateTime("2011-12-03T15:15:30Z")</code></pre>
            <pre class="pre codeblock"><code>toDateTime("2011-12-03T15:15:30.123Z")</code></pre>
            <pre class="pre codeblock"><code>toDateTime("2011-12-03T15:15:30.123+02:00")</code></pre>
            <pre class="pre codeblock"><code>toDateTime("2011-12-03T15:15:30.123-00:20")</code></pre>
            <pre class="pre codeblock"><code>toDateTime(1560762190189)</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">timeZone</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">Id of a time zone using the java implementation such as "Europe/Paris".</p>
            <p class="p">JSON format: String. It must be encapsulated in a TimeZone function.</p>
            <p class="p">Serialization format: to deserialize a time zone ID, it uses the java function java.time.ZoneId.of. <a class="xref" href="https://docs.oracle.com/javase/8/docs/api/java/time/ZoneId.html#of-java.lang.String-" target="_blank">Learn more</a>.</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">toTimeZone("&lt;time zone id&gt;")</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>toTimeZone("Europe/Paris")</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">duration</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">
            <p class="p">It represents a time-based amount of time, such as '34.5 seconds'. It models a quantity or amount of time in terms of milliseconds.</p>
            <p class="p">The supported temporal units are:</p>
            <ul class="ul" id="concept_gp3_rj5_dgb__ul_rm1_l2q_c3b">
<li class="li">milliseconds</li>
<li class="li">seconds</li>
<li class="li">minutes</li>
<li class="li">hours</li>
<li class="li">days with one day equals to 24 hours.</li>
            </ul>
            <p class="p">Years and months are not supported since they're not a fixed amount of time.</p>
            <p class="p">JSON format: String. It must be encapsulated in a toDuration function.</p>
            <p class="p">Serialization format: To deserialize a time zone ID, it uses the java function java.time.Duration.parse: the formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours. <a class="xref" href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-" target="_blank">Learn more</a>.</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">
            <p class="p">toDuration("&lt;duration in ISO-8601 format&gt;")</p>
            <p class="p">toDuration(&lt;duration in milliseconds&gt;)</p>
        </td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>toDuration("PT5S") // 5 seconds</code></pre>
            <pre class="pre codeblock"><code>toDuration(500) // 500ms</code></pre>
            <pre class="pre codeblock"><code>toDuration("PT20.345S") -- parses as "20.345 seconds"</code></pre>
            <pre class="pre codeblock"><code>toDuration("PT15M")     -- parses as "15 minutes" (where a minute is 60 seconds)</code></pre>
            <pre class="pre codeblock"><code>toDuration("PT10H")     -- parses as "10 hours" (where an hour is 3600 seconds)</code></pre>
            <pre class="pre codeblock"><code>toDuration("P2D")       -- parses as "2 days" (where a day is 24 hours or 86400 seconds)</code></pre>
            <pre class="pre codeblock"><code>toDuration("P2DT3H4M")  -- parses as "2 days, 3 hours and 4 minutes"</code></pre>
            <pre class="pre codeblock"><code>toDuration("P-6H3M")    -- parses as "-6 hours and +3 minutes"</code></pre>
            <pre class="pre codeblock"><code>toDuration("-P6H3M")    -- parses as "-6 hours and -3 minutes"</code></pre>
            <pre class="pre codeblock"><code>toDuration("-P-6H+3M")  -- parses as "+6 hours and -3 minutes"</code></pre>
        </td>
    </tr>
    <tr>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__1 "><strong class="ph b">list</strong></td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__2 ">Comma separated list of expressions using square brackets as delimiters. Polymorphism is not supported, hence all the expressions contained in the list should have the same type.</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__3 ">[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td class="entry" headers="concept_gp3_rj5_dgb__table_dhx_gns_bgb__entry__4 ">
            <pre class="pre codeblock"><code>["value1","value2"]</code></pre>
            <pre class="pre codeblock"><code>[3,5]</code></pre>
            <pre class="pre codeblock"><code>[toDuration(500),toDuration(800)]</code></pre>
        </td>
    </tr>
</tbody></table>