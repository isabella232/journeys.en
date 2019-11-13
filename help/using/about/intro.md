---
title: About Journey Orchestration
description: 
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

# About Journey Orchestration{#concept_nd3_mqt_52b}

Build real-time orchestration use cases leveraging contextual data stored in events or data sources.

The Journey Orchestration feature allows real-time orchestration powered by contextual data from events, information from the Adobe Experience Platform, or data from third-party API services. Actions in these individualized journeys currently include Email, Push Messaging, and SMS. You can also add custom actions if you're using a third-party system to send your messages.

In the event configuration tab, a **technical user** configures events expected in the journeys. The incoming events' data is normalized following the Adobe Experience Data Model (XDM). Events come from Streaming Ingestion APIs for authenticated and unauthenticated events (such as Adobe Mobile SDK events).

In the data source configuration tab, a **technical user** configures:

* The different fields exposed from the Adobe Experience Platform in the journey designer for condition building and personalization purposes.
* The additional custom data sources that you leverage in the journey designer. Custom data sources are connections between Journey Orchestration and third-party systems or services via API. You can connect a third-party system such as a loyalty system. Third-party services can be, for example, a weather API.

With the journey designer, a **business user** can easily drag and drop an entry event, add conditions and specify the action to perform.

You then create conditions based on:

* time
* data coming from the event payload
* information coming from data sources: Unified Profile data source or custom data sources

You can use the split condition to send people in the journey into different directions.

You can then send real-time personalized SMS, push notifications or emails using Adobe Campaign Standard's Transactional Messaging capabilities using action activities.

As the Journey Orchestration feature is multistep, you can create advanced scenarios. For example, after a first event and action, you can drag other events. Then, you can add a second action, place a timer to wait for some time, add a split condition to push people to two different paths and then send different messages.

**Related topics** 

* [Unified Profile Service (UPS)](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)
* [Experience Cloud XDM field definition](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html)
* [Namespace Service](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md)
* [Streaming Ingestion APIs](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)
* [Adobe Campaign Standard transactional messaging](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)
