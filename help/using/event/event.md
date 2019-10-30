---
title: Configuring an event
seo-title: Configuring an event
description: Configuring an event
seo-description: Learn how to configure an event
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

# Configuring an event {#concept_gfj_fqt_52b}

An event is linked to a person. It relates to the behavior of a person (for example, a person bought a product, visited a shop, exited a website, etc.) or something happening linked to a person (for example, a person reached 10 000 loyalty points). This is what Triggered Journeys will listen to in journeys to orchestrate the best next actions.

This configuration is **mandatory**, as Triggered Journeys is designed to listen to events, and always performed by a **technical user**.

The event configuration allows you to define the information Triggered Journeys will receive as events. You can use several events (in different steps of a journey) and several journeys can use the same event.

If you edit an event used in a draft or live journey, you can only change the name, the description or add payload fields. We strictly limit the edition of draft or live journeys to avoid breaking journeys.

## General principle {#section_r1f_xqt_pgb}

Events are POST API calls. Events are sent to the Adobe Experience Cloud Data Platform through Streaming Ingestion APIs. The URL destination of events sent through transactional messaging APIs is called an “inlet”. The payload of events follows XDM formatting. 

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by Journeys to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). There are two modes for the streaming ingestion, authenticated and unauthenticated. For details on Streaming Ingestion APIs, refer to [this link](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md).

After arriving through Streaming Ingestion APIs, events flow into an internal service called Pipeline and then in the Data Platform. If the event schema has the Unified Profile Service flag enabled and a dataset ID that also has the Unified Profile flag, it flows into the Unified Profile Service.

The Pipeline filters events which have a payload containing Triggered Journeys eventIDs (see the event creation process below) provided by Journeys and contained in event payload. These events are listened by Journeys and the corresponding journey is triggered.

## Creating a new event {#section_tbk_5qt_pgb}

Here are the main steps to configure a new event:

1. In the top bar, click **Events**. The list of events is displayed. See [the Journeys' interface](../about/aboutinterface.md#concept_rcq_lqt_52b) for more information on the interface.

 ![](assets/journey5.png)

1. Click **Add** to create a new event. The event configurator opens on the right side of the screen.

 ![](assets/journey6.png)

1. Enter a name for your event. Do not use spaces or special characters.
        <!-- Select the event type: this is where you define where the event is coming from. See [](eventtype.md#concept_oy4_jqt_52b).-->
1. Add a description to your event. This step is optional.
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) Triggered Journeys expects to receive. You will then be able to use this information in your journey. See [Defining the payload fields](eventpayload.md#concept_yrw_3qt_52b).
1. The number of journeys that use this event is displayed in the **Used in** field. You can click the **View journeys** icon to display the list of journeys using this event.
1. Add a namespace. This step is optional but recommended as adding a namespace allows you to leverage information stored in the Unified Profile Service. It defines the type of key the event has. See [Selecting the namespace](eventnamespace.md#concept_ckb_3qt_52b).
1. Define the key: choose a field from your payload fields or define a formula to identify the person associated to the event. This key is automatically setup (but can still be edited) if you select a namespace. Indeed, Triggered Journeys picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). See [Defining the event key](eventkey.md#concept_ond_hqt_52b). 
1. Add a condition. This step is optional. This allows the system to only process the events that meet the condition. The condition can only be based on information contained in the event. See [Adding a condition](eventcondition.md#concept_rbg_gqt_52b).
1. Click **Save**.

 ![](assets/journey7.png)

The event is now configured and ready to be dropped into a journey. Additional configuration steps are required to receive events. See [Additional steps to send events to Journeys](eventsteps.md#concept_xrz_n1q_y2b).
