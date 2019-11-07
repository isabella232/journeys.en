---
title: Dimensions and metrics available for Journeys
description: Learn about dimensions and metrics available for Journeys
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

# Dimensions and metrics available for Journeys {#concept_rfj_wpt_52b}

You can find here the list of every components available in Dynamic reports as well as their definitions.

**Segments** and **Profiles** components are not available for Journeys reports.

Please note that if two components are not compatible, the cell will display the value **None**. To learn more on compatibility between dimensions and metrics, refer to this [table](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility_journey.pdf).

The table below gives you the list of dimensions used in journey reports and their definitions.

## Dimensions {#MBE_table_wk4_bnj_w2b}

|Dimensions|Definition|
|--- |--- |
|Action|List of every action (**action name - action label**) used in journeys e.g. Push - Check out confirmation, Email - Rewards fidelity.|
|Data source|List of data sources (**data source name**) used to enrich data in a journey e.g. Experience platform, Reservation system.|
|Event|List of every event (**event name - event label**) used in journeys e.g. Geometrixx event - Geometrixx check out.|
|Field group|List of field groups (**field group name**) used to enrich data in journeys e.g. Profile field group, Geometrixx reservation system.|
|Journey|List of every journey (**journey name**) in test mode and live e.g. Cart abandonment, Hotel reservation notification.|
|Journey version|List of every published version of a journey (**journey name + version's number**) e.g. Cart abandonment v1, Hotel reservation notification v2.|
|Orchestration|List of every orchestration activity (**Condition, End, Timer**) defined and used in journeys. Condition: Data source condition (condition + number - label) e.g. Condition 1 - No credit card, Condition 2 - credit card holder. Time condition, date condition and split condition (condition number - split number - split details) e.g. Condition - split 1 - 50, Condition 2 - split 2 - 50.|

## Journey metrics {#MBE_p_p22_c4j_w2b}

The table below gives you the list of metrics used in journey reports, their definitions and formulas.

|Metric|Definition|Formula|
|--- |--- |--- |
|Completed|Total number of individuals that ended normally the journey.|= Journey exited|
|Completion rate|Total number of individuals that ended normally the journey compared to the total number of individuals who entered the journey.|= Journey exited/Journey entered*100|
|Current|Total number of individuals currently in the journey i.e. how many people entered minus people who exited, errors and timed out.|= Journey Entered - (../building-journeys/journey Exited + Error in Event + Error in Enrichment + Error in Action + Timeout in Action + Timeout in Event + Timeout in Enrichment + Journey in Timeout)|
|Current rate|Total number of individuals currently in the journey compared to the number of individuals who entered the journey.|= Current/Journey entered*100|
|Entered|Total number of events that occurred to start an individual entry in the journey.|= Event executed|
|Error|Total number of errors that occurred during a journey but didn't prevent the journey from being successful.|= Error in Journey + Error in Event + Error in Jump + Error in Enrichment + Error in Action + Journey in Timeout + Timeout in Action + Timeout in Event + Timeout in Enrichment|
|Error in Action|Total number of errors that occurred for actions.|= Error in Action + Timeout in Action|
|Error in Enrichment|Total number of errors that occurred for a data enrichment when calling a data source/field group.|= Error in Enrichment + Timeout in Enrichment|
|Error in Event|Total number of errors that occurred for events.|= Error in Event + Timeout in Event|
|Error rate|Total number of errors that occurred during a journey compared to the total number of occurrences in the journey.|=((Error in Event + Error in Enrichment + Error in Action + Journey in Timeout + Timeout in Action + Timeout in Event + Timeout in Enrichment)/(Executed action + Executed Enrichment + Executed Event + Executed orchestration))*100|
|Executed Action|Total number of actions executed for a journey.|= Executed action|
|Executed Enrichment|Total number of enrichments executed by calling a data source to get specific field groups.|= Executed enrichment|
|Executed Event|Total number of actions executed for a journey.|= Executed event|
|Executed Orchestration|Total number of orchestration objects (end, timer, condition) executed for a journey.|= Condition executed|
|Failed|Total number of journeys that were not successfully executed. |= Error in Journey + Journey in timeout|
|Failed rate|Total number of journeys that were not successfully executed compared to the number of run journeys. |= Error in Journey + Journey in timeout / Journey entered*100 |

## Delivery metrics {#delivery-metrics}

The table below gives you the list of metrics used in journey
reports, their definitions and formulas.

|Metric|Definition|Formula|
|--- |--- |--- |
|Blacklisted|Number of recipients who have declared an email as spam or junk.|failureReason=8, failureType = 2|
|Blacklisted rate|Total number of messages marked as blacklisted compared to messages sent.|Blacklisted / Sent|
|Bounces + errors|Total of errors cumulated during delivery and automatic return processing in relation to the total number of sent messages.|status=2|
|Bounce + error rate|Total number of messages that bounced compared to messages sent.|Bounces / Sent|
|Click|Number of times a content was clicked in a delivery.|trackingUrlType = 1, 10 or 11|
|Click through rate|Total number of clicks in a delivery compared to the number of delivered messages.|Unique Clicks / Delivered|
|Delivered|Number of messages successfully sent, in relation to the total number of sent messages.|status=1|
|Delivered rate|Total number of messages successfully delivered compared to messages sent.|Delivered / Sent|
|Error|Total number of errors that occurred during a journey but didn't prevent the journey from being successful.|= Error in Journey + Error in Event + Error in Jump + Error in Enrichment + Error in Action + Journey in Timeout + Timeout in Action + Timeout in Event + Timeout in Enrichment|
|Hard bounce|Total number of permanent errors, such as a wrong email address.|failureType=2 AND failureReason=8|
|Hard bounce rate|Total number of deliveries that failed due to permanent errors compared to messages sent.|Hard bounces/ Sent|
|Mirror page|Number of recipients who clicked on the mirror page link.|trackingUrlType=6|
|Mirror page rate|Total number of clicks on the mirror page link compared to the total delivered messages.|Mirror page / Delivered|
|Open|Number of times a message was opened in a delivery.|(trackingUrlType=2) + Unique(trackingUrlType=1,2,3,6,10,11) - Unique(trackingUrlType=2)|
|Open Rate|Total number of opened messages compared to the number of delivered messages.|Unique Opens / Delivered|
|Quarantine|Number of messages that bounced and resulted in the quarantine of the address.|isQuarantine=true|
|Quarantine Rate|Total number of quarantines compared to messages sent.|Quarantine / Sent|
|Rejected|Number of messages classified as spam by the SMTP servers.|failureReason=20, failureType=2|
|Rejected rate|Total number of messages marked as rejected compared to messages sent.|Rejected / Sent|
|Processed/sent|Total number of sends for the delivery.|Delivered + Bounces|
|Soft bounce|Total number of temporary errors, such as a full inbox.|failureType=1|
|Soft bounce rate|Total number of deliveries that failed due to temporary reason compared to messages sent.|Soft Bounces/ Sent|
|Unique clicks|Number of recipients who clicked on a content in a delivery.|Unique clicks are calculated using ThetaSketch concepts.|
|Unique opens|Number of recipients who opened the delivery.|unique(@trackingUrlType=1,2,3,6,10,11)|
|Unsubscribed|Number of clicks on the unsubscription link.|trackingUrlType=3|
|Unsubscribe rate|Total number of unsubscriptions by recipient compared to the delivered messages.|Unsubscribed/Delivered|
