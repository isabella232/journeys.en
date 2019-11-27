---
title: Advanced use case pre-requisites
description: Learn pre-requisites for the journey advanced use case
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

# Advanced use case pre-requisites {#concept_xwn_qcy_w2b}

For our use case, we have designed three Adobe Campaign Standard transactional messaging templates. We are using event transactional messaging templates. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard is configured to send emails and push notifications.

The Experience Cloud ID is used as the key to identify the customer in the hotel reservation system.

Events are sent from the customers' mobile phone when they detected near a beacon. You need to design a mobile application to send events from the customer's mobile phone to the Mobile SDK.

The Loyalty member field is a custom field and was added in XDM for our specific organization ID.
