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

Then create an event “arrive at store” as well as a condition ”checks any abandoned cart” looking for an experience event so need to use advanced mode.

## Creating an event


## Creating a condition 

In string value look for and specified value.

`In (“addToCart”, #{field reference from experience event})`

Looking for all experience events for this user specified in the last 7 days, returns a Boolean.

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

## Checking that a product is in store

And checking that the product is in stock.

1. In Inventory, look for quantity field and specify that it should be greater than 0.

`#{Inventory.fieldgroup3.quantity} > 0`

1. Then specify the location

`#{ArriveLumaStudio._acpevangelists1.location.location}`

1. Then specify SKU:  

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

1. Add another path.

1. If so, send notification with engagement offer.Configure messages accordingly and use personalization data to enhance the message target.

    ```

    In (“completePurchase”, #{ExperiencePlatformDataSource
                            .ExperienceEventFieldGroupDemoCommons
                            .experienceevent
                            .all(
                            inLastDays(currentDataPackField.timestamp, 7 ))
                            ._acpevangelists1
                            .productData
                            .productInteraction })

    ```

    