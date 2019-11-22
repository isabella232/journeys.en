---
title: Using the journey designer
description: Learn on using the journey designer
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

# Using the journey designer {#concept_m1g_5qt_52b}

The journey Home menu allows you to view the **list of journeys**. Create a new journey or click on a existing one to open the **journey designer's interface**. The designer is made up of the following zones: the palette, the canvas and the activity configuration pane.

## The journey list {#journey_list}

The **journey list** allows you to view all your journeys at once, see their status and perform basic actions. You can duplicate, stop or delete your journeys. Depending on the journey, certain actions might not be available. For example, you can't stop or delete a stopped journey. You can also use the search bar to search for a journey.

The **Filters** can be accessed by clicking on the filter icon on the top left of the list. The filters menu allows you to filter the displayed journeys according to different criteria (status, the ones you created, the ones modified in the last 30 days, latest versions only etc.). You can also choose to only display the journeys that use a particular event, field group or action. Columns displayed on the list can be configured. All filters and columns are saved per user.

![](../assets/journey74.png)

All the versions of your journeys appear in the list with the version number. See [Journey versions](../building-journeys/journeyversions.md#concept_ldc_k55_zgb).

![](../assets/journey37.png)

>[!NOTE]
>
>To open a journey's canvas in a different browser tab, hold the **Control** or **Command key** and click on the journey.

## The palette {#palette}

The **palette** is on the left-hand side of the screen. All available activities are sorted into several categories: **Events**, **Orchestration** and **Actions**. You can expand/collapse the different categories by clicking on their name. To use an activity in your journey, drag and drop it from the palette into your canvas. You can also double-click on an activity in the palette to add it to the canvas, at the next step available. You have to configure each activity added from the palette before publishing the journey. If you drop an activity in the canvas and do not finish its configuration, it will stay in the canvas but a red warning will indicate that the configuration is not finished for this activity.

>[!NOTE]
>
>Note that there are rules when setting up a journey. Unallowed configuration will be discarded. For example, you cannot place actions in parallel, link an activity to a previous step to create a loop, start a journey with something else than an event, etc.

 ![](../assets/journey38.png)

## The canvas {#canvas}

The **canvas** is the central zone in the journey designer. It is in this zone that you can drop your activities and configure them. Click on an activity in the canvas to configure it. This opens the activity configuration pane on the right-hand side. You can zoom in and out by using the "+" and "-" buttons on the top right. In the canvas, all activities allow you to add a next step after them, except **End** activities (see [End](../building-journeys/end.md)). 

 ![](../assets/journey39.png)

## The activity configuration pane {#configuration_pane}

The **activity configuration pane** appears when you click on an activity in the palette. Fill in the required fields. Click on the **Delete** icon to delete the activity. Click on **Cancel** to cancel the modifications or **Ok** to confirm. To delete activities, you can also select one activity (or several) and press the backspace key. Pressing the escape key will close the activity configuration pane.

In the canvas, your action and event activities are represented by an icon with the name of the event or action displayed underneath. In the activity configuration pane, you can use the **Label** field to add a suffix to the activity name. These labels will help you contextualize the use of events and actions, especially when you use the same event or action several times in your journey. You will also be able to see the labels you added in the Journey Orchestration reporting.

 ![](../assets/journey59bis.png)

## The top bar actions {#top_actions}

Depending on the journey's status, you can perform different actions on your journey using the buttons available in the top right corner: **Publish**, **Duplicate**, **Delete**, **Journey properties**, **Test**. These buttons appear when no activity is selected. Some buttons will appear contextually. The test mode log button appears when test mode is activated (see [Testing your journey](../building-journeys/journeytesting.md)). The reporting button appears when the journey is live, stopped or finished.

 ![](../assets/journey41.png)

## The use of paths in the canvas {#paths}

Several activities (**Condition**, **Action** activities) allow you to define a fallback action in case of an error or timeout. In the activity configuration pane, check the box: **Add an alternative path in case of a timeout or an error**. Another path is added after the activity. The timeout duration is defined in the journey's properties (see [Changing properties](../building-journeys/journeyproperty.md#concept_prq_wqt_52b)) by an admin user. For example, if an email takes too long to be sent or is in error, you can decide to send an SMS.

 ![](../assets/journey42.png)

Various activities (event, action, wait) allow you to add several paths after them. To do this, place your cursor on the activity and click on the "+" symbol. Only event and wait activities can be set in parallel. If several events are set in parallel, the chosen path will be the one of the first event happening. 

When listening to an event, we recommend that you do not wait for the event indefinitely. It is not mandatory, just a best practice. If you want to listen to one or several events only during a certain time, you will place one or several events and a wait activity in parallel. See [Advanced usage](../building-journeys/journeyevent.md#section_vxv_h25_pgb).

To delete the path, place your cursor on it and click the **Delete arrow** icon.

 ![](../assets/journey42ter.png)
