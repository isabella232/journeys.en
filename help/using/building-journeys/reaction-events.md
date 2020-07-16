---
title: Reactions events
description: Learn about reaction events
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

# Reaction events {#section_dhx_gss_dgb}

Among the different event activities available in the palette, you will find the built-in **Reactions** event. This activity allows you to react to tracking data related to a message sent with email, SMS or push activities within the same journey. This information comes from transactional messaging in Adobe Campaign Standard. We capture this information in real-time at the moment it is shared with the Adobe Experience Platform. For push notifications, you can react to clicked, sent or failed messages. For SMS messages, you can react to sent or failed messages. For emails, you can react to clicked, sent, opened or failed messages.

You can also use this mechanism to perform an action when there is no reaction to your messages. To do this, create a second path parallel to the reaction activity and add a wait activity. If there is no reaction during the period defined in the wait activity, the second path will be chosen. You can choose to send, for example, a follow-up message. 

Note that you can only use a reaction activity in the canvas if there is an email, push or SMS activity before.

See [About action activities](../building-journeys/about-action-activities.md).

 ![](../assets/journey45.png)

Here are the different steps to configure the reaction events:

1. Add a **[!UICONTROL Label]** to the reaction. This step is optional.
1. From the drop-down list, select the action activity you want to react to. You can select any action activity positioned in the previous steps of the path.
1. Depending on the action you selected (an email, SMS or a push notification), choose what you want to react to. 
1. You can define a condition as an optional step. For example, after an email action, you can decide to create two paths, one with a reaction event to track clicks only for VIP customers and one with a reaction event to track clicks performed by women.

>[!NOTE]
>
>Reactions events work with Adobe Campaign Standard, wether it's deployed on AWS or Azure servers.
>
>Reaction events cannot track email, SMS or push actions that take place in a different journey.
>
>Reaction events track clicks on links of the type "tracked" (see this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Unsubscription and mirror page links are not taken into account.

>[!IMPORTANT]
>
>Email clients such as Gmail allow image blocking. Emails opens are tracked using a 0-pixel image included in the email. If images are blocked, email opens will not be taken into account.

## Segment qualification events {#segment-qualification}

This activity allows your journey to listen to the entrances and exits of profiles in Adobe Experience Platform segments in order to make individuals enter or move forward in a journey. For more information on segment creation, refer to this [section](../segment/about-segments.md).

Let's say you have a "silver customer" segment. With this activity, you can make all new silver customers enter a journey and send them a series of personalized messages.

This type of event can be positioned as the first step or later in the journey.

If the segment is streamed with the High Frequency Audiences option of Adobe Experience Platform, entrance and exits are listened to in real time. If the segment is not streamed, entrances and exits are taken into account at segment calculation time.

1. Unfold the **Events** category and drop a **Segment qualification** activity into your canvas.

   ![](../assets/segment5.png)

1. Add a **Label** to the activity. This step is optional.

1. Click in the **Segment** field and select the segments you want to leverage. 

   ![](../assets/segment6.png)

1. In the **Behavior** field, choose is you want to listen to segment entrances, exits or both.

1. Select a namespace. This is only needed if the event is positionned as the first step of the journey.

   ![](../assets/segment7.png)

The payload contains the following context information, which you can use in conditions and actions:

* the behavior (entrance, exit)
* the timestamp of qualification
* the segment id

When using the expression editor in a condition or action that follows a **Segment qualification** activity, you have access to the **SegmentQualification** node. You can choose between the **Last qualification time** and the **status** (enter or exit).

See [Condition activity](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## Advanced usage: events with a wait in parallel{#section_vxv_h25_pgb}

**How can you listen to an event only during a certain time?**

An event activity positioned in the journey listens to events indefinitely. To listen to an event only during a certain time, you must add a wait activity parallel to the event path. The journey will then listen to the event during the time specified in the wait activity. If an event is received during that period, the person will flow in the event path. If not, the customer will flow into the wait path.

For example, you sent a welcome first push to a customer and you want to send a meal discount push only if the customer enters the restaurant within the next 6 hours. To do this, you will create a second path (parallel to the restaurant event one) with a 6-hour wait activity. If the restaurant event is received less than 6 hours after the welcome push, the meal discount push activity is sent. If no restaurant event is received within the next 6 hours, the person flows through the wait path.

 ![](../assets/journeyuc2_31.png)
