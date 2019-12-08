---
title: Time zone management
description: Learn about time zone management
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


# Time zone management {#timezone_management}

Time zone definition is available in the following activities:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

If the entry event of the journey has a namespace, meaning that the journey can reach the Real-time Customer Profile service of the Data Platform, the time zone is pre-defined with the one specified in the profile of the individual flowing in the journey. If the individual's profile does not contain a time zone, the instance's time zone is used. You can contact your administrator to know the instance time zone.

![](../assets/journey73.png)

The time zone can also be fixed. Clear the pre-defined time zone and pick one from the drop-down list. If you use a fixed time zone, it will be the same for all individuals entering the journey. 

![](../assets/journey72.png)

Finally, the time zone can be dynamic for each person entering the step. In this case, you will use the expression editor to select where you want the system to get this information (it can be from an event or a data source). See [](../expression/expressionadvanced.md).


The start and end dates of a journey cannot be linked to a specific time zone. They are automatically associated to the instance's time zone.
