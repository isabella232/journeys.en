---
product: Journeys
audience: end-user
user-guide-title: Journeys Help
index: n
---

# Journeys Help {#using}

+ [Product documentation](journeys-home.md)
+ Starting with Journeys {#starting-with-journeys}
  + [About Journeys](using/intro.md)
  + [User Process](using/aboutprocess.md)
  + [The Journeys' interface](using/aboutinterface.md)
  + [Ending a journey](using/aboutending.md)
  + [Managing your users' access to Journeys](using/usermanagement.md)
  + [Troubleshooting](using/troubleshooting.md)
+ About events {#events-journeys}
  + [Configuring an event](using/event.md)
  + [Defining the payload fields](using/eventpayload.md)
  + [Selecting the namespace](using/eventnamespace.md)
  + [Defining the event key](using/eventkey.md)
  + [Adding a condition](using/eventcondition.md)
  + [Previewing the payload](using/eventpayloadpreview.md)
  + [Additional steps to receive events](using/eventsteps.md)
+ About datasources {#data-source-journeys}
  + [Configuring a datasource](using/ds.md)
  + [Defining the payload fields](using/dsfield.md)
  + [Adobe Experience Platform data source](using/dsplatform.md)
  + [External data sources](using/dsexternal.md)
+ About custom actions {#custom-action-journeys}
  + [Configuring a custom action](using/custom.md)
  + [Custom action limitations](using/customlimitations.md)
  + [URL configuration](using/customurl.md)
  + [Configuring the authentication](using/customauthentication.md)
  + [Defining the message parameters](using/customparameters.md)
+ About building journeys {#building-journeys}
  + [Building a journey](using/journey.md)
  + [The journey designer's interface](using/journeyinterface.md)
  + [The journey's properties](using/journeyproperty.md)
  + [Events activities](using/journeyevent.md)
  + [Orchestration activities](using/journeyorchestration.md)
  + [Action activities](using/journeyaction.md)
  + [Testing and publishing the journey](using/journeypublication.md)
  + [Journey versions](using/journeyversions.md)
+ Building advanced conditions {#building-advanced-conditions-journeys}
  + [Building advanced conditions](using/expressionadvanced.md)
  + [Generalities](using/expressiongeneralities.md)
  + [Constants](using/expressionconstants.md)
  + [Field references](using/expressionfields.md)
  + [Operators](using/expressionoperators.md)
  + [Functions](using/expressionfunctions.md)
  + Main functions {#main-functions-journey}
    + Adobe Experience Platform {#adobe-experience-platform}
      + [getBestSendTime](using/functions/functiongetbestsendtime.md)
      + [inSegment](using/functions/functioninsegment.md)
    + Aggregation {#aggregation}
      + [avg](using/functions/functionavg.md)
      + [count](using/functions/functioncount.md)
      + [countOnlyNull](using/functions/functioncountonlynull.md)
      + [countWithNull](using/functions/functioncountwithnull.md)
      + [distinctCount](using/functions/functiondistinctcount.md)
      + [distinctCountwithNull](using/functions/functiondistinctcountwithnull.md)
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
      + [toTimeZone](using/functions/functiontotimezone.md)
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
      + [updateTimeZone](using/functions/functionupdatetimezone.md)
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
+ About journeys reports{#journey-reports}
  + [Building your Journeys reports](using/reporting.md)
  + [Creating your Journeys reports](using/reportingcreating.md)
  + [Dimensions and metrics available for Journeys](using/reportingdimensions.md)
+ Use cases{#use-cases-journeys}
  + Simple use case{#use-case-simple}
    + [Introduction](using/uc1intro.md)
    + [Pre-requisites](using/uc1prereq.md)
    + [Configuring the event](using/uc1event.md)
    + [Configuring the data source](using/uc1ds.md)
    + [Building the journey](using/uc1journey.md)
  + Advanced use case{#use-case-advanced}
    + [Introduction](using/uc2intro.md)
    + [Pre-requisites](using/uc2prereq.md)
    + [Configuring the events](using/uc2event.md)
    + [Configuring the data source](using/uc2ds.md)
    + [Building the journey](using/uc2journey.md)
  + [Leveraging fatigue scores](using/uc3.md)
  