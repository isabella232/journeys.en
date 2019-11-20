---
title: Defining the message parameters
description: Learn how to define the message parameters
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

# Defining the message parameters {#concept_wy4_bf1_2gb}

In the **Message parameters** section, paste an example of the JSON payload to send to the external service.

You will be able to define if the type of the parameter is right (e.g.: string, integer, etc.).

You will also have a choice between specifying a parameter is a constant or a variable:

* Constant means that the value of the parameter is defined in the action configuration pane by a technical persona. The value will be always the same across journeys. It will not vary and the marketer won’t see it when using the custom action in the journey. It could be for example an ID the third-party system expects. In that case, the field on the right of the toggle constant/variable is the value passed.
* Variable means the value of the parameter will vary. The marketer using this custom action in a journey will be free to pass the value he wants or to specify where to retrieve the value for this parameter (e.g.: from the event, from the Data Platform…). In that case, the field on the right of the toggle constant/variable is the label the marketer will see in the journey to name this parameter.
