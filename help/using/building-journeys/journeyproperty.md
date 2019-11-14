---
title: The journey's properties
description: Learn about the journey's properties
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


# The journey's properties {#concept_prq_wqt_52b}

Click on the pencil icon, in the top right to access the journey's properties.

You can change the name of the journey, add a description, choose start and end dates and define a **Timeout and error** duration if you are admin. 

 ![](../assets/journey32.png)

When editing an action or condition activity, you can define an alternative path in case of error or timeout. If the processing of the activity interrogating a third-party system exceeds the timeout duration defined in the journey's properties (**Timeout and  error** field in conditions and actions), the second path will be chosen to perform a potential fallback action. 

Authorized values are between 1 and 30 seconds.

We recommend that you define a very short **Timeout and error** value if your journey is time sensitive (ex: reacting to the real-time location of a person) because you cannot delay your action for more than a few seconds. If your journey is less time sensitive, you can put a longer value to give more time to the system called to send a valid response.

Note that a journey timeout can also be defined. It does not display in the interface and cannot be configured. This timeout will stop the progress of individuals in the journey 30 days after they enter a journey. This means that an individual's journey cannot last longer than 30 days. After 30 day timeout period, the individual's data is be deleted. Individual still flowing in the journey at the end of the timeout period will be stopped and they will be taken into account as errors in reporting.

By default, new journeys allow re-entrance. You can uncheck the option for “one shot” journeys, for example if you want to offer a one-time gift when a person enters a shop. In that case, you don't want the customer to be able to re-enter the journey and receive the offer again.

When a journey "ends", it will have the status **Finished**. The journey will stop letting new individuals enter the journey. Persons already in the journey will finish the journey normally.
