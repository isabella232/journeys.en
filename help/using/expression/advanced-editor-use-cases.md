---
title: Using the advanced expression editor
description: Learn how to build advanced expressions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# Using the advanced expression editor

The Advanced expression editor can be used to create conditions to allow you to filter users in your journeys. These conditions enable you to target users on time, date, localization duration, or action such as purchase or abandonment of carts so that they can be retargeted in the journey.

Events starts with @, data sources with #.

## Building conditions on Experience Events

The advanced expression editor is mandatory to perform queries on time series such as a list of purchases or past clicks on messages. Such queries cannot be performed using the simple editor.

The experience events are retrieved from the Experience Platform as a collection in reverse chronological order, hence:

* first function will return the most recent event
* last function will return the oldest one.

For example, let's say you want to target customers with a cart abandonment in the last 7 days to send a message when the customer is getting near a store, with an offer on items he wanted thatare in store.

**You need to build the following conditions:**

First of all, target customers browsed the online store but did not finalize order in the last 7 days.

Then create an event “arrive at store” as well as a condition to check any abandoned cart looking for an experience event so need to use advanced mode.

**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`

**The following expression looks for all  events for this user specified in the last 7 days:**

Then it selects all the addtocart events that did not transform into a completePurchase. 

The specified timestamp is acting as the date time value, the second is number of days.

    ```
    In ( “addToCart”, #{ExperiencePlatformDataSource
                    .ExperienceEventFieldGroupDemoCommons
                    .experienceevent
                    .all(
                    inLastDays(currentDataPackField.timestamp, 7 ))
                    ._acpevangelists1
                    .productData
                    .productInteraction } )

    And
    Not(In ( “completePurchase”, #{ExperiencePlatformDataSource
                    .ExperienceEventFieldGroupDemoCommons
                    .experienceevent
                    .all(
                    inLastDays(currentDataPackField.timestamp, s7 ))
                    ._acpevangelists1
                    .productData
                    .productInteraction } )
    ```

This expression returns a boolean.

**Now let's build an expression checking that the product is in stock**

* In Inventory, this expression looks for quantity field of a product and specify that it should be greater than 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* This expression specifies the location.

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Then specify SKU:  

    ```
    #{ExperiencePlatformDataSource
                    .ExperienceEventFieldGroupDemoCommons
                    .experienceevent
	                .first(
                     currentDataPackField. _acpevangelists1.productData.productInteraction == “addToCart”
                    )
                    ._acpevangelists1
                    .SKU}
    ```

From there you can add another path in your journey and send notification with engagement offer. Configure messages accordingly and use personalization data to enhance the message target.


## Examples of string manipulation 

**In conditions**

Condition that checks the place from which the geofence event has been triggered is "Arlington":

    ```
    @{GeofenceEntry.placeContext.POIinteraction.POIDetail.name} == "Arlington"
    ```

Explanation: This is a strict string comparison (case sensitive), equivalent to a query in simple mode that uses ‘equal to’ with ‘Is sensitive’ checked.

The same query with ‘Is sensitive’ unchecked will generate the following expression in advanced mode:

    ```
    equalIgnoreCase(@{GeofenceEntry.placeContext.POIinteraction.POIDetail.name}, "Arlington")
    ```

**In actions**

The following expression allows you to define the CRM ID in an action personalization field :

    ```
    substr(@{MobileAppLaunch._myorganization.identification.crmid}, 1, lastIndexOf(@{MobileAppLaunch._myorganization.identification.crmid}, "}"))
    ```

Explanation: This example uses substr and lastIndexOf functions to remove curly braces that enclose the CRM ID passed with a mobile app launch event.
