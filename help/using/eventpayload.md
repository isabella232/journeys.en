---
title: Defining the payload fields
seo-title: Defining the payload fields
description: Defining the payload fields
seo-description: Learn about defining the payload fields
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: y
internal: n
snippet: y
---

# Defining the payload fields {#concept_yrw_3qt_52b}

The payload definition allows you to choose the information the system expects to receive from the event in your journey and the key to identify which person is associated to the event. The payload is based on the Experience Cloud XDM field definition. For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Select an XDM schema from the list and click on the **Payload** field or on the **Edit** icon.

    ![](assets/journey8.png)

    All the fields defined in the schema are displayed. The list of fields varies from one schema to another. You can search for a specific field or use the filters to display all nodes and fields or only the selected fields. According to the schema definition, some fields may be mandatory and pre-selected. You cannot unselect them. 

    ![](assets/journey9.png)

1. Select the fields you expect to receive from the event. These are the fields which the business user will leverage in the journey. They must also include the key that will be used to identify the person associated to the event (see [Defining the event key](eventkey.md#concept_ond_hqt_52b)). An example of field that can be used in the journey is the phone model (__device > model__).

    ![](assets/journey10.png)

    >[!NOTE]
    >
    >The **eventID** field is automatically added in the list of fields selected so that Triggered Journeys can identify the event. The system pushing the event should not generate an ID, it should use the one available in the payload preview. See [Previewing the payload](eventpayloadpreview.md#concept_jgf_4yk_4fb).

1. When you're done selecting the needed fields, click **Save** or press **Enter**.

    ![](assets/journey11.png).

The number of selected fields appears in the **Payload** field.

    ![](assets/journey12.png)
