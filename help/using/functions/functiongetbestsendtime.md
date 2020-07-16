---
title: getBestSendTime
description: Learn about the function getBestSendTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# getBestSendTime {#getBestSendTime}

Provides a predictive time of the best time for delivering an email to an individual. 

This function uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default time will apply. For more information, see [](../building-journeys/wait-activity.md).

To use this function, a [namespace](../event/selecting-the-namespace.md) is needed.

>[!NOTE]
>
>Note that the best send time score can be unavailable if there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

## Category

Adobe Experience Platform

## Function syntax

`getBestSendTime(<parameters>)`

## Parameters

|Parameter|Description|Type|
|--- |--- |--- |
|amount of time|Number of hours to consider from the current time (max : 168) to optimize email sending|`<integer>`|
|optimization type|"open" or "click"|`<string>`|
|default time in hours to wait|In case the predictive send time scores are not available|`<integer>`|

## Signature and returned type

`getBestSendTime(<integer>,<string>,<integer>)`

Returns a dateTime.

## Example

getBestSendTime(12,"open",8)

Explanation :

The function will return the best time to send a message in the next 12 hours, in order to optimize the probability for the individual in the journey instance to open it. In case there is not enough data to perform the calculation, the returned time is in 8 hours from the current time.
