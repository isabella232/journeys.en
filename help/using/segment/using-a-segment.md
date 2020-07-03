---
title: Using a segment
description: Learn how to use a segment
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

# Using segments in your journeys {#using-a-segment}

This section explains how to use a segment in a journey condition or action.
To learn how to use a **Segment qualification** event in your journey, refer to [Events activities](../building-journeys/event-activities.md#segment-qualification).

The following steps allow you to use a segment in a journey condition. For journey action mapping, the principle is similar.

1. Open a journey, drop a **Condition** activity and choose the **Data Source Condition**.
   ![](../assets/journey47.png)

1. Click **Add a path** for each extra path needed. For each path, click the **Expression** field.

   ![](../assets/segment3.png)

1. On the left side, unfold the **SegmentQualification** or **Segments** node. Drag and drop the segment you want to use for your condition. 

   From the **SegmentQualification** node, you can choose between the **Last qualification time** and the **status** (enter or exit).

   ![](../assets/segment8.png)

   When you drop an element from the **Segments** node, the condition on the segment is true by default.

   ![](../assets/segment4.png)

For more information on journey conditions and how to use the simple expression editor, refer to [Condition activities](../building-journeys/condition-activity.md#about_condition).
