---
title: Troubleshooting
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

# Troubleshooting{#concept_nlv_bcv_2fb}

Here are various tools that you can use to troubleshoot your journeys.

## Checking that events are properly sent{#section_rqz_11t_dgb}

The starting point of a journey is always an event. You can perform tests using tools such as Postman.

You can check if the API call you send through these tools is sent correctly or not. If you get an error back, it means that your call has an issue. Check the payload again, the header (and especially the organization ID) and the URL.

## Tracking if people enter the journey{#section_x4v_zzs_dgb}

Journey orchestration reporting measures people's entrances in a journey in real-time.

If you're successfully sending the event but see no entrance in the journey, it means that something goes wrong between the event sending and the event reception in the journey.

Here are a few things and administrator should double-check:

*   Are you sure the journey where you expect the incoming event is live?
*   Did you save your event before copying the payload from the payload preview?
*   Did you follow the Streaming Ingestion APIs payload structure and correctly pasted the event payload in the "data" section of the Streaming Ingestion APIs event payload?

## Tracking how people navigate through the journey{#section_l5y_yzs_dgb}

Journey orchestration reporting measures the progress of individuals inside a journey. It's easy to identify where and why a person got stopped.

Here are a few things to check:

*   Is it due to a condition excluding the person? For example, the condition is "gender = male" and the person is a woman. This check can be performed by a business user if the condition is not too complex.
*   Is it due to a call to a data source not responding? An administrator can test direct calls the data source and check the answer received.

## Tracking that messages are sent successfully{#section_qb1_yzs_dgb}

If individuals flow the right way in the journey but don't receive messages, you can check if:

* Transactional Messaging has correctly taken into account the request to send the message. A business user can access the transactional message supposed to be sent and check if the time of the latest execution corresponds to the execution time your journey.
* Transactional messaging has successfully sent the message. In the sending logs of the transactional message, you can see the status of each execution. You can see if it's green, red and what was the issue. A business user can access this screen and send the logs to an administrator for further investigations.

## Testing journeys before publication{#section_fhm_gxb_fhb}

Before publishing your journey, you can use the test mode to test your journey's behavior. This will allow you to see how your test profiles flow in the journey, what data is retrieved and if they finish the journey successfully. For more information, refer to [Testing your journey](../building-journeys/journeypublication.md#concept_mtc_lrt_52b__section_ctr_lqk_fhb).

## Troubleshooting Streaming Ingestion APIs{#section_epp_42s_w3b}

Refer to this [page](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md).
