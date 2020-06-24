---
title: Segment Trigger activity
description: Learn xxxx
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

# Segment Trigger activity {#segment-trigger-activity}

## About the Segment Trigger activity {#about-segment-trigger-actvitiy}

The Segment Trigger activity allows you to make all individuals belonging to an Experience Platform segment enter a journey.

Let's say you have a Gold customer segment on Experience Platform. With the Segment Trigger activity, you can make all individuals belonging to the Gold customer segment enter a journey and send them a series of personalized messages, and build conditions based on this segment.

>[!NOTE]
>
>Note that it is currently not possible to test a journey starting with a Segment Trigger activity.

## Configuring the activity {#configuring-segment-trigger-activity}

1. Unfold the **[!UICONTROL Orchestration]** category and drop a **[!UICONTROL Segment Trigger]** activity into your canvas.

    The activity must be positioned as the first step of a journey.

1. Configure the activity **[!UICONTROL Scheduler type]**.

    By default, the segment will enter the journey 1 hour after it is published. If you want to make the segment enter the journey on a specific date/time or on a recurring basis, select the desired option from the list.

    Several options are available for each option to help you refine the segment entry time (start date, repetition, time zone, etc.)

    ![](../assets/segment-trigger-schedule.png)

1. In the **!UICONTROL Segment]** field, choose one or multiple Experience Platform segment that will enter the journey, the click **!UICONTROL Save]**.

    ![](../assets/segment-trigger-segment-selection.png)

1. In the **[!UICONTROL Namespace]** field, choose the key to associate to the namespace in order to identify the individuals. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

    >[!NOTE]
    >
    >Only the individuals configured with the selected key will be picked to enter the journey. For example, if you choose "ECID" as the namespace key, individuals with the "email address" key will not be taken into account to enter the journey.

1. Click **[!UICONTROL Ok]** to confirm.

You can then leverage available activities to build your journey and publish it. Individuals belonging to the segment will enter the journey at the date/time specified in the Segment Trigger activity scheduler.

Keep in mind that Experience Platform segments are calculated either once a day >(**batch** segments) or in real-time (**streamed** segments). If the selected segment is streamed, the individuals belonging to this segment will be calculated in real-time. If the segment is not streamed, only the individuals belonging to the segment at its calculation time will enter the journey.
