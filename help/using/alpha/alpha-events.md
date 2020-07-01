---
title: Simplified events
description: Learn more about simplified events.
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

# Simplified events{simplified-events}

We have simplified the way you set up Experience events. We're introducing a new method that does not require the use of an eventID. When you set up your event in Journey Orchestration, you can now define a rule-based event.

This new type of event does not generate an eventID. Using the simple expression editor, you now simply define a rule which will be used by the system identify the relevant events that will trigger your journeys. This rule can be based on any field available in the event payload, for example the profile's location or the number of items added to the profile's cart.

This new method is mostly transparent for users. The only change is a new field in the event definition screen.

1. From the left menu, click the **Admin** icon, then click **Events**. The list of events is displayed. 

   ![](../assets/alpha-event1.png)

1. Click **Add** to create a new event. The event configuration pane opens on the right side of the screen.

   ![](../assets/alpha-event2.png)

1. Enter the name of your event. You can also add a description.

   ![](../assets/alpha-event3.png)

1. In the new **Event ID type** field, select **Rule Based**. 

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >The **System Generated** type is the existing method that requires an eventID. See [this section](../event/about-events.md).

1. Define the **Schema** and payload **Fields**. See [this section](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >When you select the **System Generated type**, only schemas that have the eventID type mixin are available. When you select the **Rule Based** type, all schemas are available.

1. Click inside the **Event ID condition** field. Using the simple expression editor, define the condition that will be used by the system to identify the events that will trigger your journey.

   ![](../assets/alpha-event6.png)

   In our example, we wrote a condition based on the profile's city. This means that whenever the system receives an event that matches this condition (**City** field and **Paris** value), it will pass it to Journey Orchestration.

1. Define the **Namespace** and **Key**. See [Selecting the namespace](../event/selecting-the-namespace.md) and [Defining the event key](../event/defining-the-event-key.md).

   ![](../assets/alpha-event7.png)

The other steps for event configuration and journey creation remain unchanged. 

The event is now configured and ready to be dropped into a journey like any other event. Every time an event that matches the rule is sent to the system, it is passed to Journey Orchestration to trigger your journeys.  

