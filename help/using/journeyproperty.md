---
title: The journey's properties
seo-title: The journey's properties
description: The journey's properties
seo-description: Learn about the journey's properties
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

You can change the name of the journey, add a description, choose start and end dates and define a timeout duration. By default, new journeys allow re-entrance. You can uncheck the option for example if you want to offer a one-time gift when entering a shop. In that case, you don't want the customer to be able to re-enter the journey and receive the offer again.

    ![](assets/journey32.png)

When a journey "ends", it will have the status **Finished**. The journey will stop reacting to events. 

When editing an action or condition activity, you can define an alternative path in case of error or timeout. If the processing of the activity exceeds the timeout duration defined in the journey's properties (**Condition and Action Timeout** field), the second path will be chosen to perform the fallback action.
