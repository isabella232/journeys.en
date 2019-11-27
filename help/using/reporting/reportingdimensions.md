---
title: Metrics and dimensions
description: Learn about dimensions and metrics available for Journey Orchestration
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

# Metrics and dimensions {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Delivery data will only be populated if you have Adobe Campaign Standard.

You can find here the list of every components available in Dynamic reports as well as their definitions.

The table below gives you the list of dimensions used in journey reports and their definitions.

To learn more on compatibility between dimensions and metrics, refer to [this page](../assets/dynamic_report_compatibility_journey.pdf).

## Dimensions {#MBE_table_wk4_bnj_w2b}

|Dimensions|Definition|
|--- |--- |
|**Action**|List of every action (**action name - action label**) used in journeys e.g. Push - Check out confirmation, Email - Rewards fidelity.|
|**Data source**|List of data sources (**data source name**) used to enrich data in a journey e.g. Experience platform, Reservation system.|
|**Event**|List of every event (**event name - event label**) used in journeys e.g. Geometrixx event - Geometrixx check out.|
|**Field group**|List of field groups (**field group name**) used to enrich data in journeys e.g. Profile field group, Geometrixx reservation system.|
|**Journey**|List of every journey (**journey name**) in test mode and live e.g. Cart abandonment, Hotel reservation notification.|
|**Journey version**|List of every published version of a journey (**journey name + version's number**) e.g. Cart abandonment v1, Hotel reservation notification v2.|
|**Orchestration**|List of every orchestration activity (**Condition, End, Wait**) defined and used in journeys. Condition: Data source condition (condition + number - label) e.g. Condition 1 - No credit card, Condition 2 - credit card holder. Time condition, date condition and split condition (condition number - split number - split details) e.g. Condition - split 1 - 50, Condition 2 - split 2 - 50.|

## Journey metrics {#MBE_p_p22_c4j_w2b}

The table below gives you the list of metrics used in journey reports, their definitions and formulas.

|Metric|Definition|
|--- |---|
|**Completed**|Total number of individuals that ended normally the journey.|
|**Completion rate**|Total number of individuals that ended normally the journey compared to the total number of individuals who entered the journey.|
|**Current**|Total number of individuals currently in the journey i.e. how many people entered minus people who exited, errors and timed out.|
|**Current rat**e**|Total number of individuals currently in the journey compared to the number of individuals who entered the journey.|
|**Entered**|Total number of events that occurred to start an individual entry in the journey.|
|**Error**|Total number of errors that occurred during a journey but didn't prevent the journey from being successful.|
|**Error in Action**|Total number of errors that occurred for actions.|
|**Error in Enrichment**|Total number of errors that occurred for a data enrichment when calling a data source/field group.|
|**Error in Event**|Total number of errors that occurred for events.|
|**Error rate**|Total number of errors that occurred during a journey compared to the total number of occurrences in the journey.|
|**Executed Action**|Total number of actions executed for a journey.|
|**Executed Enrichment**|Total number of enrichments executed by calling a data source to get specific field groups.|
|**Executed Event**|Total number of actions executed for a journey.|
|**Executed Orchestration**|Total number of orchestration objects (end, wait, condition) executed for a journey.|
|**Failed**|Total number of journeys that were not successfully executed. |
|**Failed rate**|Total number of journeys that were not successfully executed compared to the number of run journeys. |

## Delivery metrics {#delivery-metrics}

The table below gives you the list of metrics used in journey
reports, their definitions and formulas.

|Metric|Definition|
|--- |--- |
|**Blacklisted**|Number of recipients who have declared an email as spam or junk.|
|**Blacklisted rate**|Total number of messages marked as blacklisted compared to messages sent.|
|**Bounces + errors**|Total of errors cumulated during delivery and automatic return processing in relation to the total number of sent messages.|
|**Bounce + error rate**|Total number of messages that bounced compared to messages sent.|
|**Click**|Number of times a content was clicked in a delivery.|
|**Click through rate**|Total number of clicks in a delivery compared to the number of delivered messages.|
|**Delivered**|Number of messages successfully sent, in relation to the total number of sent messages.|
|**Delivered rate**|Total number of messages successfully delivered compared to messages sent.|
|**Error**|Total number of errors that occurred during a journey but didn't prevent the journey from being successful.|
|**Hard bounce**|Total number of permanent errors, such as a wrong email address.|
|**Hard bounce rate**|Total number of deliveries that failed due to permanent errors compared to messages sent.|
|**Mirror page**|Number of recipients who clicked on the mirror page link.|
|**Mirror page rate**|Total number of clicks on the mirror page link compared to the total delivered messages.|
|**Open**|Number of times a message was opened in a delivery.|
|**Open Rate**|Total number of opened messages compared to the number of delivered messages.|
|**Quarantine**|Number of messages that bounced and resulted in the quarantine of the address.|
|**Quarantine Rate**|Total number of quarantines compared to messages sent.|
|**Rejected**|Number of messages classified as spam by the SMTP servers.|
|**Rejected rate**|Total number of messages marked as rejected compared to messages sent.|
|**Processed/sent**|Total number of sends for the delivery.|
|**Soft bounce**|Total number of temporary errors, such as a full inbox.|
|**Soft bounce rate**|Total number of deliveries that failed due to temporary reason compared to messages sent.|
|**Unique clicks**|Number of recipients who clicked on a content in a delivery.|
|**Unique opens**|Number of recipients who opened the delivery.|
|**Unsubscribed**|Number of clicks on the unsubscription link.|
|**Unsubscribe rate**|Total number of unsubscriptions by recipient compared to the delivered messages.|
