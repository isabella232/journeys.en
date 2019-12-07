---
title: Functions
description: Learn about functions
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

# Functions {#concept_p1r_qj5_dgb}

A function can have different signatures (a different set of ordered parameters). A function signature can have 0-N expressions as ordered parameters.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Each function has a specific returned type. 

Here is the list of supported functions.

## Main functions

| Category    | Function              |
|-------------|-----------------------|
| Adobe Experience Platform | [](../functions/functiongetbestsendtime.md)|
| Adobe Experience Platform | [](../functions/functioninsegment.md)|
| Aggregation | [](../functions/functionavg.md)|
| Aggregation | [](../functions/functioncount.md)|
| Aggregation | [](../functions/functioncountonlynull.md)|
| Aggregation | [](../functions/functioncountwithnull.md)|
| Aggregation | [](../functions/functiondistinctcount.md)|
| Aggregation | [](../functions/functiondistinctcountwithnull.md)|
| Aggregation | [](../functions/functionmax.md)|
| Aggregation | [](../functions/functionmin.md)|
| Aggregation | [](../functions/functionsum.md)|
| Conversion  | [](../functions/functiontobool.md)|
| Conversion  | [](../functions/functiontodatetime.md)|
| Conversion  | [](../functions/functiontodatetimeonly.md)|
| Conversion  | [](../functions/functiontodecimal.md)|
| Conversion  | [](../functions/functiontoduration.md)|
| Conversion  | [](../functions/functiontointeger.md)|
| Conversion  | [](../functions/functiontostring.md)|
| Date        | [](../functions/functioncurrenttimeinmillis.md)|
| Date        | [](../functions/functioninlastdays.md)|
| Date        | [](../functions/functioninlasthours.md)|
| Date        | [](../functions/functioninlastmonths.md)|
| Date        | [](../functions/functioninlastyears.md)|
| Date        | [](../functions/functioninnextdays.md)|
| Date        | [](../functions/functioninnexthours.md)|
| Date        | [](../functions/functioninnextmonths.md)|
| Date        | [](../functions/functioninnextyears.md)|
| Date        | [](../functions/functionnow.md)|
| Date        | [](../functions/functionnowwithdelta.md)|
| Date        | [](../functions/functionsethours.md)|
| Date        | [](../functions/functionsetdays.md)|
| List        | [](../functions/functiondistinct.md)|
| List        | [](../functions/functiondistinctcount.md)|
| List        | [](../functions/functionin.md)|
| List        | [](../functions/functionlistsize.md)|
| List        | [](../functions/functionserializelist.md)|
| List        | [](../functions/functionsort.md)|
| Math        | [](../functions/functionrandom.md)|
| Math        | [](../functions/functionround.md)|
| String      | [](../functions/functionconcat.md)|
| String      | [](../functions/functioncontain.md)|
| String      | [](../functions/functioncontainwithignorecase.md)|
| String      | [](../functions/functionendwith.md)|
| String      | [](../functions/functionendwithignorecase.md)|
| String      | [](../functions/functionequalignorecase.md)|
| String      | [](../functions/functionindexof.md)|
| String      | [](../functions/functionisempty.md)|
| String      | [](../functions/functionisnotempty.md)|
| String      | [](../functions/functionlastindexof.md)|
| String      | [](../functions/functionlength.md)|
| String      | [](../functions/functionlower.md)|
| String      | [](../functions/functionmatchregexp.md)|
| String      | [](../functions/functionnotequalignorecase.md)|
| String      | [](../functions/functionreplace.md)|
| String      | [](../functions/functionreplaceall.md)|
| String      | [](../functions/functionstartwith.md)|
| String      | [](../functions/functionstartwithignorecase.md)|
| String      | [](../functions/functionsubstr.md)|
| String      | [](../functions/functiontrim.md)|
| String      | [](../functions/functionupper.md)|
| String      | [](../functions/functionuuid.md)|

## Collection management functions {#section_ig2_hb5_pgb}

The expression language also introduces a set of functions to query collections.

These functions are explained below. In the following examples, let’s use the event payload containing a collection:

```

                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}

```

**The function "all(`<condition>`)"**

The **all** function enables the definition of a filter on a given collection by using a boolean expression.

   ```
   <listExpression>.all(<condition>)
   ```

For example, among all the app users, you can get the ones using IOS 13 (boolean expression “app used == IOS 13"). The result of this function is the filtered list containing items matching the boolean expression (example: app user 1, app user 34, app user 432).

In a Data Source Condition activity you can check if the result of the **all** function is null or not. You can also combine this **all** function with other functions such as **count**. For more information, see [Data Source Condition activity](../building-journeys/condition.md#data_source_condition).

**Example 1:**

We want to check if a user has installed a specific version of an application. For this we get all the push notification tokens associated to mobile applications for which the version is 1.0. Then, we perform a condition with the **count** function to check that the returned list of tokens contains at least one element.

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
   ```

The result is true.

**Example 2:**

Here we use the **count** function to check if there are push notification tokens in the collection.

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
   ```

The result will be true.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journey Orchestration sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

   >[!NOTE]
   >
   >When the filtering condition in the **all()** function is empty, the filter will return all the elements in the list. **However, in order to count the number of elements of a collection, the all function is not required.**


   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
   ```

   The result of the expression is **3**.

**Example 3:**

Here we check if an individual has not received any communication within the last 24 hours. We filter the collection of experience events retrieved from the ExperiencePlatform datasource, using two expressions based on two elements of the collection. In particular, the timestamp of the event is compared to the dateTime returned by the **nowWithDelta** function.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

The result will be true if there is no experience event matching the two conditions.

**Example 4:**

Here we want to check if an individual has launched at least once an application in the last 7 days, in order for instance to trigger a push notification inviting him to start a tutorial.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```


<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**currentEventField** is only available when manipulating event collections and **currentDataPackField** 
>when manipulating data source collections. When processing collections with **all**, **first** and **last**, we
>loop on each element of the collection one by one. **currentEventField** and **currentDataPackField**
>correspond to the element being looped.

**The functions "first(`<condition>`)" and "last(`<condition>`)"**

The **first** and **last** functions also enable the definition of a filter on the collection while returning the first/last element of the list that meets the filter.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Example 1:** 

This expression returns the first push notification token associated to mobile applications for which the version is 1.0.

   ```
   @{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
   ```

The result is "token_1".

**Example 2:** 

This expression returns the last push notification token associated to mobile applications for which the version is 1.0.

   ```
   @{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
   ```

   The result is "token_2".

   >[!NOTE]
   >
   >The experience events are retrieved from the Experience Platform as a collection in reverse chronological order, hence :
   >* **first** function will return the most recent event
   >* **last** function will return the oldest one.

**Example 3:**

We check whether the first (most recent) Adobe Analytics event with a non-zero value for DMA ID has a value equal to 602.

   ```
   #{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
   currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
   ```

**The function "at(`<index>`)"**

The **at** function allows you to reference a specific element in a collection according to an index.
Index 0 is the first index of the collection. 

_`<listExpression>`.at(`<index>`)_

**Example:** 

This expression returns the second push notification token of the list.

   ```
   @{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
   ```

The result is "token_2".

## Conditional instruction (if, then, else){#section_cdz_lsk_w3b}

The conditional instruction (if, then, else) is supported in the advanced editor. It allows to define more complex expressions. It is composed of the following elements:

* **if**: the condition to be evaluated first.
* **then**: the expression to be evaluated in case the result of the condition evaluation is true.
* **else**: the expression to be evaluated in case the result of the condition evaluation is false.

>[!NOTE]
>
>Parentheses are required around all the expressions.

   ```
   if  (<expression1>)
   then
      (<expression2>)
   else
      (<expression3>)
   ```

`<expression1>` must return a **boolean**.

`<expression2>` and `<expression3>` must have the same type or compatible types. The supported signatures and returned types are:

   ```
   boolean,boolean : boolean
   dateTime,dateTime : dateTime
   dateTimeOnly,dateTimeOnly : dateTimeOnly
   decimal,integer : decimal
   integer,decimal : integer
   integer,decimal : decimal
   duration,duration : duration
   string,string : string
   listBoolean,listBoolean : listBoolean
   listDateTime,listDateTime : listDateTime
   listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
   listDecimal,listDecimal : listDecimal
   listInteger,listInteger : listInteger
   listString,listString : listString
   ```

**Usage**

The conditional instruction allows you to optimize the journey workflow by reducing the number of condition activities. For example, within the same action activity, you can specify two alternatives for a field definition using only one condition expression.

Example for an action activity (for a field that expects a string as the result of the conditional instruction):

   ```
   if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
   then
      ('apns')
   else
      ('fcm')
   ```
