---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: n
---

# Journey Orchestration Help {#using}

+ [Product documentation](journey-orchestration-home.md)
+ What's new {#release-notes}
  + [Release Notes](using/release-notes/release-notes.md)
+ Starting with Journey Orchestration {#starting-with-journeys}
  + [About Journey Orchestration](using/about/about-about-orchestration-activities.md)
  + [Get started](using/about/get-started.md)
  + [User interface](using/about/user-interface.md)
  + [Access management](using/about/access-management.md)
  + [Troubleshooting](using/about/troubleshooting.md)
+ Configuring an event {#events-journeys}
  + [About events](using/event/event.md)
  + [Defining the payload fields](using/event/eventpayload.md)
  + [Selecting the namespace](using/event/eventnamespace.md)
  + [Defining the event key](using/event/eventkey.md)
  + [Adding a condition](using/event/eventcondition-activity.md)
  + [Previewing the payload](using/event/eventpayloadpreview.md)
  + [Additional steps to send events](using/event/eventsteps.md)
+ Configuring a data source {#data-source-journeys}
  + [About data sources](using/datasource/about-data-sources.md)
  + [Field groups](using/datasource/field-groups.md)
  + [Adobe Experience Platform data source](using/datasource/adobe-experience-platform-data-source.md)
  + [External data sources](using/datasource/external-data-sources.md)
+ Configuring an action {#action-journeys}
  + [About actions](using/action/action.md)
  + [Working with Adobe Campaign](using/action/working-with-adobe-campaign.md)
  + Using a third-party system {#action-third-party}
    + [About custom action configuration](using/action/about-custom-action-configuration.md)
    + [Custom action limitations](using/action/custom-action-limitations.md)
    + [URL configuration](using/action/url-configuration.md)
    + [Defining the message parameters](using/action/defining-the-message-parameters.md.md)
+ Building a journey {#building-journeys}
  + About journey building {#about-journey-building}
    + [Creating a journey](using/building-journeys/journey.md)
    + [Using the journey designer](using/building-journeys/using-the-journey-designer.md)
    + [Changing properties](using/building-journeys/changing-properties.md)
    + [Journey versions](using/building-journeys/journey-versions.md)
    + [Terminating a journey](using/building-journeys/terminating-a-journey.md)
    + [Time zone management](using/building-journeys/timezone-management.md)
  + Activities {#about-journey-building}
    + [Events activities](using/building-journeys/event-activities.md)
    + Orchestration activities {#orchestration-activities}
      + [About orchestration activities](using/building-journeys/about-orchestration-activities.md)
      + [Condition activity](using/building-journeys/condition-activity.md)
      + [End activity](using/building-journeys/end-activity.md)
      + [Wait activity](using/building-journeys/wait-activity.md)
    + Action activities {#action-activities}
      + [About action activities](using/building-journeys/about-action-activities.md)
      + [Using Adobe Campaign actions](using/building-journeys/journey-working-with-adobe-campaign.md)
      + [Using custom actions](using/building-journeys/using-custom-actions.md)
  + [Testing the journey](using/building-journeys/testing-the-journey.md)
  + [Publishing the journey](using/building-journeys/publishing-the-journey.md)
+ Using the advanced expression editor {#building-advanced-conditions-journeys}
  + [About the advanced expression editor](using/expression/expressionadvanced.md)
  + [Generalities](using/expression/generalities.md)
  + [Data types](using/expression/data-types.md)
  + [Field references](using/expression/field-references.md)
  + [Operators](using/expression/operators.md)
  + [Functions](using/expression/functions.md)
  + Function details {#main-functions-journey}
    + Adobe Experience Platform {#adobe-experience-platform}
      + [getBestSendTime](using/functions/functiongetbestsendtime.md)
      + [inSegment](using/functions/functioninsegment.md)
    + Aggregation {#aggregation}
      + [avg](using/functions/functionavg.md)
      + [count](using/functions/functioncount.md)
      + [countOnlyNull](using/functions/functioncountonlynull.md)
      + [countWithNull](using/functions/functioncountwithnull.md)
      + [distinctCount](using/functions/functiondistinctcount.md)
      + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
      + [max](using/functions/functionmax.md)
      + [min](using/functions/functionmin.md)
      + [sum](using/functions/functionsum.md)
    + Conversion {#conversion}
      + [toBool](using/functions/functiontobool.md)
      + [toDateTime](using/functions/functiontodatetime.md)
      + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
      + [toDecimal](using/functions/functiontodecimal.md)
      + [toDuration](using/functions/functiontoduration.md)
      + [toInteger](using/functions/functiontointeger.md)
      + [toString](using/functions/functiontostring.md)
    + Date {#date}
      + [currentTime​InMillis](using/functions/functioncurrenttimeinmillis.md)
      + [inLastDays](using/functions/functioninlastdays.md)
      + [inLastHours](using/functions/functioninlasthours.md)
      + [inLastMonths](using/functions/functioninlastmonths.md)
      + [inLastYears](using/functions/functioninlastyears.md)
      + [inNextDays](using/functions/functioninnextdays.md)
      + [inNextHours](using/functions/functioninnexthours.md)
      + [inNextMonths](using/functions/functioninnextmonths.md)
      + [inNextYears](using/functions/functioninnextyears.md)
      + [now](using/functions/functionnow.md)
      + [nowWithDelta](using/functions/functionnowwithdelta.md)
      + [setHours](using/functions/functionsethours.md)
      + [setDays](using/functions/functionsetdays.md)
    + List {#list}
      + [distinct](using/functions/functiondistinct.md)
      + [distinctWithNull](using/functions/functiondistinctwithnull.md)
      + [in](using/functions/functionin.md)
      + [listSize](using/functions/functionlistsize.md)
      + [serializeList](using/functions/functionserializelist.md)
      + [sort](using/functions/functionsort.md)
    + Math {#math}
      + [random](using/functions/functionrandom.md)
      + [round](using/functions/functionround.md)
    + String {#string}
      + [concat](using/functions/functionconcat.md)
      + [contain](using/functions/functioncontain.md)
      + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
      + [endWith](using/functions/functionendwith.md)
      + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
      + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
      + [indexOf](using/functions/functionindexof.md)
      + [isEmpty](using/functions/functionisempty.md)
      + [isNotEmpty](using/functions/functionisnotempty.md)
      + [lastIndexOf](using/functions/functionlastindexof.md)
      + [length](using/functions/functionlength.md)
      + [lower](using/functions/functionlower.md)
      + [matchRegExp](using/functions/functionmatchregexp.md)
      + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
      + [replace](using/functions/functionreplace.md)
      + [replaceAll](using/functions/functionreplaceall.md)
      + [startWith](using/functions/functionstartwith.md)
      + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
      + [substr](using/functions/functionsubstr.md)
      + [trim](using/functions/functiontrim.md)
      + [upper](using/functions/functionupper.md)
      + [uuid](using/functions/functionuuid.md)
+ Building your reports{#journey-reports}
  + [About journey reports](using/reporting/reporting.md)
  + [Creating your journey reports](using/reporting/reporting-creating.md)
  + [Metrics and dimensions](using/reporting/reporting-dimensions.md)
+ Use cases{#use-cases-journeys}
  + Simple use case{#use-case-simple}
    + [About the simple use case](using/usecase/simple-uc-about-about-orchestration-activities.md)
    + [Configuring the event](using/usecase/simple-uc-event.md)
    + [Configuring the data source](using/usecase/simple-uc-data-source.md)
    + [Building the journey](using/usecase/simple-uc-journey.md)
  + Advanced use case{#use-case-advanced}
    + [About the advanced use case](using/usecase/advanced-uc-about-about-orchestration-activities.md)
    + [Configuring the events](using/usecase/advanced-uc-event.md)
    + [Configuring the data sources](using/usecase/advanced-uc-data-source.md)
    + [Building the journey](using/usecase/advanced-uc-journey.md)
  + [Leveraging fatigue scores](using/usecase/leveraging-fatigue-scores.md)
  