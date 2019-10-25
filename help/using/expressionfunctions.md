---
title: Functions
seo-title: Functions
description: Functions
seo-description: Learn about the function Functions
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

# Functions {#concept_p1r_qj5_dgb}

A function can have different signatures (a different set of ordered parameters). A function signature can have 0-N expressions as ordered parameters.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)
Each function has a specific return data type. Here is the list of supported functions.

## Main functions

| Category    | Function              |
|-------------|-----------------------|
| AEP         | [getBestSendTime](functiongetbestsendtime.md)|
| AEP         | [inSegment](functioninsegment.md)|
| Aggregation | [avg](functionavg.md)|
| Aggregation | [count](functioncount.md)|
| Aggregation | [countOnlyNull](functioncountonlynull.md)|
| Aggregation | [countWithNull](functioncountwithnull.md)|
| Aggregation | [discountCount](functiondistinctcount.md)|
| Aggregation | [discountCountwithNull](functiondistinctcountwithnull.md)|
| Aggregation | [max](functionmax.md)|
| Aggregation | [min](functionmax.md)|
| Aggregation | [sum](functionsum.md)|
| Conversion  | [toBool](functiontobool.md)|
| Conversion  | [toDateTime](functiontodatetime.md)|
| Conversion  | [toDateTimeOnly](functiontodatetimeonly.md)|
| Conversion  | [toDecimal](functiontodecimal.md)|
| Conversion  | [toDuration](functiontoduration.md)|
| Conversion  | [toInteger](functiontointeger.md)|
| Conversion  | [toString](functiontostring.md)|
| Conversion  | [toTimeZone](functiontotimezone.md)|
| Date        | [currentTime​InMillis](functioncurrenttimeinmillis.md)|
| Date        | [inLastDays](functioninlastdays.md)|
| Date        | [inLastHours](functioninlasthours.md)|
| Date        | [inLastMonths](functioninlastmonths.md)|
| Date        | [inLastYears](functioninlastyears.md)|
| Date        | [inNextDays](functioninnextdays.md)|
| Date        | [inNextHours](functioninnexthours.md)|
| Date        | [inNextMonths](functioninnextmonths.md)|
| Date        | [inNextYears](functioninnextyears.md)|
| Date        | [now](functionnow.md)|
| Date        | [nowWithDelta](functionnowwithdelta.md)|
| Date        | [setHours](functionsethours.md)|
| Date        | [setDays](functionsetdays.md)|
| Date        | [updateTimeZone](functionupdatetimezone.md)|
| List        | [distinct](functiondistinct.md)|
| List        | [distinctWithNull](functiondistinctcount.md)|
| List        | [in](functionin.md)|
| List        | [listSize](functionlistsize.md)|
| List        | [serializeList](functionserializelist.md)|
| List        | [sort](functionsort.md)|
| Math        | [random](functionrandom.md)|
| Math        | [round](functionround.md)|
| String      | [concat](functionconcat.md)|
| String      | [contain](functioncontain.md)|
| String      | [containWithIgnoreCase](functioncontainwithignorecase.md)|
| String      | [endWith](functionendwith.md)|
| String      | [endWithIgnorecase](functionendwithignorecase.md)|
| String      | [equalIgnoreCase](functionequalignorecase.md)|
| String      | [indexOf](functionindexof.md)|
| String      | [isEmpty](functionisempty.md)|
| String      | [isNotEmpty](functionisnotempty.md)|
| String      | [lastIndexOf](functionlastindexof.md)|
| String      | [length](functionlength.md)|
| String      | [lower](functionlower.md)|
| String      | [matchRegExp](functionmatchregexp.md)|
| String      | [notEqualIgnoreCase](functionnotequalignorecase.md)|
| String      | [replace](functionreplace.md)|
| String      | [replaceAll](functionreplaceall.md)|
| String      | [startWith](functionstartwith.md)|
| String      | [startWithIgnoreCase](functionstartwithignorecase.md)|
| String      | [substr](functionsubstr.md)|
| String      | [trim](functiontrim.md)|
| String      | [upper](functionupper.md)|
| String      | [uuid](functionuuid.md)|

## Collection management functions {#section_ig2_hb5_pgb}

The expression language also introduces a set of functions to query collections. These functions are explained below. Let’s use the following collection for a few examples:

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

The **all** function enables the definition of a filter on a given collection. For example, among all the app users, you can get the ones using IOS 13 (boolean expression “app used = IOS 13"). The result of this function is the filtered list containing items matching the boolean expression (example: app user 1, app user 34, app user 432).
You can then use this in a condition to check if the result of the **all** function is null or not. You can also combine this **all** function with other functions such as **count**.

**"All + Count" condition example 1:** we want to check if a user has installed a specific version of an application. For this we get all the push notification tokens associated to mobile applications for which the version is 1.0. Then, we perform a condition with the count function to check that the returned list of tokens contains at least one element.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all&#8203;(currentEventField.application.version == "1.0").token}) > 0`

**"All + Count" example 2:** here we use the count function to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name})`

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

<!--A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journeys sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`

**The functions "first(`<condition>`)" and "last(`<condition>`)"**
The **first** and **last** functions enable the definition of a filter on a given collection while returning the first/last element of the list that meets the filter. 

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)` _

**Example 1:** return the first push notification token associated to mobile applications for which the version is 1.0.

`@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token`

The result will be:

`"token_1"`

**currentEventField** is only available when manipulating event collections and **currentDataPackField** when manipulating data source collections. When processing collections with all, first and last, we loop on each element of the collection one by one. **currentEventField** and **currentDataPackField** correspond to the element being looped.

**Example 2:** return the last push notification token associated to mobile applications for which the version is 1.0.

`@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}`

The result will be:

`"token_2"`

**The function "at(`<index>`)"**
The **at** function allows you to reference a specific element in a collection according to an index. 

_`<listExpression>`.at(`<index>`)_

**Example 1:** return the second push notification token of the list.

`@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}`

The result will be:

`"token_2"`

## Conditional instruction (if, then, else){#section_cdz_lsk_w3b}

The conditional instruction (if, then, else) is supported in the advanced editor. It allows to define more complex conditions. It is composed of the following elements:

* **if**: the **boolean** condition to be evaluated first.`
* **then**: the expression to be evaluated in case the result of the boolean condition evaluation is true.`
* **else**: the expression to be evaluated in case the result of the boolean condition evaluation is false.`

>[!NOTE]
>
>Curly brackets are required around all the expressions.

   ```

   if  (`<expression1>`)
   then
      (`<expression2>`)
   else
      (`<expression3>`)
   ```

`<expression1>` must return a **boolean**.

`<expression2>` and `<expression3>` must have the same type or compatible types. The supported signatures and returned types are:

   ```

   <boolean><boolean> : <boolean>
   <dateTime><dateTime> : <dateTime>
   <dateTimeOnly><dateTimeOnly> : <dateTimeOnly>
   <decimal><integer> : <decimal>
   <integer><decimal> : <integer>
   <integer><decimal> : <decimal>
   <duration><duration> : <duration>
   <string><string> : <string>
   <listBoolean><listBoolean> : <listBoolean>
   <listDateTime><listDateTime> : <listDateTime>
   <listDateTimeOnly><listDateTimeOnly> : <listDateTimeOnly>
   <listDecimal><listDecimal> : <listDecimal>
   <listInteger><listInteger> : <listInteger>
   <listString><listString> : <listString>
   ```

**Usage**

The conditional instruction allows you to optimize the journey workflow by reducing the number of condition activities. For example, within the same action activity, you can specify two alternatives for a field using only one condition expression.

Example for an action activity (for a field that expects a string as the result of the conditional instruction):

   ```

   if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
   then
      ('APNS')
   else
      ('FCM')
   ```
