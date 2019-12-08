---
title: Using Adobe Campaign actions
description: Learn about Adobe Campaign actions
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

# Using Adobe Campaign actions {#using_campaign_action}

If you have Adobe Campaign Standard, the following out-of-the-box action activities are available: **Email**, **Push** and **SMS**. 

>[!NOTE]
>
>For this, you need to configure the built-in action. Refer to [](../action/working-with-adobe-campaign.md).

For each of these channels, you select an Adobe Campaign Standard Transactional Messaging **template**. Indeed, Journey Orchestration is not a message sending solution. For the built-in email, SMS and push channels, we rely on Transactional Messaging to execute message sending. It means that if you want to use a certain message template in your journeys, you must publish it in Adobe Campaign Standard. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) to learn how to use this feature.

![](../assets/journey59.png)

You can use an event (also known as real-time) or profile transactional messaging template.

>[!NOTE]
>
>When we send real-time transactional messages (rtEvent) or when we route messages with a third-party system thanks to a custom action, a specific setup is required for fatigue, blacklist or unsubscription management. For example, if an attribute "blacklist" or "unsubscribe" is stored in the Platform or in a third-party system, a condition will have to be added before the message sending to check this condition.

When you select a template, all the fields expected in the message payload are displayed in the activity configuration pane under **Address** and **Personalization data**. You need to map each of these fields with the field you want to use, either from the event or from the data source. You can also use the advanced expression editor to pass a value manually, perform data manipulation on retrieved information (for example convert a string to uppercase) or use functions such as "if, then, else". See [](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## Email and SMS {#section_asc_51g_nhb}

For **Email** and **SMS**, the parameters are identical.

>[!NOTE]
>
>For email, if you're using a profiles transactional template, the unsubscription mechanism is handled out-of-the-box by Campaign Standard. You simply add an **Unsubscription link** content block in the template ([learn more](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). If you're using an event-based template (rtEvent), you need to add, in the message, a link passing the person's email in the URL parameter and pointing to an unsubscription landing page. You need to create this landing page and make sure the person's decision to unsubscribe is transmitted to Adobe.

First, you need to choose a transactional messaging template. See [](../building-journeys/about-action-activities.md).

Two categories are available: **Address** and **Personalization Data**.

You can easily define where to retrieve the **Address** or the **Personalization Data** using the interface. You can browse through events and available data source’s fields. You can also use the advanced expression editor for more advanced use cases such as using a data source that requires the passing of parameters or performing manipulations. See [](../expression/expressionadvanced.md). 

**Address**

>[!NOTE]
>
>This category is only visible if you select an "event" transactional message. For "profile" messages, the **Address** field is automatically retrieved from Adobe Campaign Standard by the system.

These are the fields the system requires to know where to send the message. For an email template, it's the email address. For an SMS, it's the mobile phone number.

![](../assets/journey61.png)

**Personalization data**

>[!NOTE]
>
>You cannot pass a collection in personalization data. If the transactional email or SMS expects collections, it will not work. Also note that the personalization data has an expected format (example: string, decimal, etc.). You must be careful to respect these expected formats. 

These are the fields expected by the Adobe Campaign Standard message. These fields can be used to personalize the message, apply conditional formatting, or pick a specific message variant. 

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Prior to using the push activity, your mobile app needs to be configured along with Campaign Standard to send push notifications. Use this [article](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) to take the necessary implementation steps for mobile.

First, you need to choose a mobile app from the drop-down list and a transactional message. See [](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Two categories are available: **Target** and **Personalization Data**.

**Target**

>[!NOTE]
>
>This category is only visible if you select an event message. For profile messages, the **Target** fields are automatically retrieved by the system using the reconciliation performed by Adobe Campaign Standard.

In this section, you need to define the **Push platform**. The drop-down list allows you to select **Apple Push Notification Server** (iOS) or **Firebase Cloud Messaging** (Android). You can alternatively select a specific field from an event or a data source, or define an advanced expression.

You also need to define the **Registration Token**. The expression depends on how the token is defined in the event payload or in other Journey Orchestration information. It can be a simple field or a more complex expression in case the token is defined in a collection for instance:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**Personalization Data**

>[!NOTE]
>
>You cannot pass a collection in personalization data. If the transactional push expects collections, it will not work. Also note that the personalization data has an expected format (example: string, decimal, etc.). You must be careful to respect these expected formats.

These are the fields expected by the transactional template used in your Adobe Campaign Standard message. These fields can be used to personalize your message, apply conditional formatting, or pick a specific message variant.
