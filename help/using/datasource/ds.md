---
title: Configuring a data source 
description: Learn how to configure a data source 
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

# Configuring a data source {#concept_s1s_dqt_52b}

The data source configuration is always performed by a **technical user**.
The data source configuration allows you to define a connection to a system to retrieve additional information that will be used in your journeys, for:

* condition definition
* parameter and personalization data in actions
* custom timer definition
* custom timezone definition

This configuration is not required if your journeys only leverage local data coming from an event payload. For example, if your journey is composed of an event followed by an email activity that only uses data from the event, there is no need to configure a data source.
There are two types of data sources:

* The pre-configured Experience Platform data source that defines the connection to the Unified Profile Service. This is a built-in data source. See [Adobe Experience Platform data source](../datasource/dsplatform.md#concept_zrb_nqt_52b).
* The external data sources that allow you to define a connection to external systems. These are the ones you can create. See [External data sources](../datasource/dsexternal.md#concept_t2s_kqt_52b).

For each data source, you define the information to retrieve using field groups. See [Field groups](../datasource/dsfield.md#concept_ntl_ypt_52b).

Here are the main data source configuration steps:

1. In the top bar, click **Data Sources**. The list of data sources is displayed. See [The Journeys' interface](../about/aboutinterface.md#concept_rcq_lqt_52b) for more information on the interface.

  ![](../assets/journey18.png)

1. Then you can either add field groups to the built-in data source (see [Adobe Experience Platform data source](../datasource/dsplatform.md#concept_zrb_nqt_52b)) or create a new external data source (see [External data sources](../datasource/dsexternal.md#concept_t2s_kqt_52b)) and associated field groups (see [Field groups](../datasource/dsfield.md#concept_ntl_ypt_52b)).

 ![](../assets/journey22.png)

1. Click **Save**. The data source is now configured and ready to be used in your journeys.
