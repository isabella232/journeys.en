---
title: Additional steps to send events to Journey Orchestration
description: Learn about additional steps to send events to Journey Orchestration
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


# Additional steps to send events to Journey Orchestration {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>When creating an event, Journey Orchestration automatically generates an ID for this event. The system pushing the event should not generate an ID, it should use the one available in the payload preview. See [](../event/eventpayloadpreview.md#concept_jgf_4yk_4fb).

To configure events to be sent to **Streaming Ingestion APIs** and to be used in Journey Orchestration, you need to follow these steps:

1. Get the inlet URL from the Data Platform APIs (see [Streaming Ingestion APIs](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)).
1. Copy the payload from the payload preview in the **Event** menu. See [](../event/eventpayload.md#concept_yrw_3qt_52b).

You then need to configure the data system that pushes events to Streaming Ingestion APIs using the payload you copied:

1. Set up a POST API call to the Streaming Ingestion APIs URL (called an inlet).
1. Use the payload you copied from Journey Orchestration in the body ("data section") of the API call to Streaming Ingestion APIs. See below for an example
1. Determine where to get all the variables present in the payload. Example: if the event if supposed to convey the address, the payload pasted will show "address": "string". "string" should be replaced by the variable that will automatically populate the right value, the email of the person to send a message to. Note that in the payload preview, in the **Header** section, we autofill many values expected to facilitate your work.
1. Select "application/json" as a body type.
1. Pass your IMS ORG ID in the header using the key "x-gw-ims-org-id". For the value, use your IMS ORG ID ("XXX@AdobeOrg").

Here is an example of a Streaming Ingestion APIs event:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

To facilitate the identification of the place where to paste the "data" part, you can use a JSON visualization tool such as [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

To troubleshoot Streaming Ingestion APIs, refer to this [page](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md).
