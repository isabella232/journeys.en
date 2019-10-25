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
+ Events in Journeys {#events-journeys}
  + [Configuring an event](using/event.md)
  + [Defining the payload fields](using/eventpayload.md)
  + [Selecting the namespace](using/eventnamespace.md)
  + [Defining the event key](using/eventkey.md)
  + [Adding a condition](using/eventcondition.md)
  + [Previewing the payload](using/eventpayloadpreview.md)
  + [Additional steps to receive events](using/eventsteps.md)
+ Configuring a datasource {#data-source-journeys}
  + [Configuring a datasource](using/ds.md)
  + [Defining the payload fields](using/dsfield.md)
  + [Adobe Experience Platform data source](using/dsplatform.md)
  + [External data sources](using/dsexternal.md)
+ Configuring a custom action {#custom-action-journeys}
  + [Configuring a custom action](using/custom.md)
  + [Custom action limitations](using/customlimitations.md)
  + [URL configuration](using/customurl.md)
  + [Configuring the authentication](using/customauthentication.md)
  + [Defining the message parameters](using/customparameters.md)
+ Building a journey {#building-journeys}
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
      + [getBestSendTime](using/functiongetbestsendtime.md)
      + [inSegment](using/functioninsegment.md)
    + Aggregation {#aggregation}
      + [avg](using/functionavg.md)
      + [count](using/functioncount.md)
      + [countOnlyNull](using/functioncountonlynull.md)
      + [countWithNull](using/functioncountwithnull.md)
      + [distinctCount](using/functiondistinctcount.md)
      + [distinctCountwithNull](using/functiondistinctcountwithnull.md)
      + [max](using/functionmax.md)
      + [min](using/functionmin.md)
      + [sum](using/functionsum.md)
    + Conversion {#conversion}
      + [toBool](using/functiontobool.md)
      + [toDateTime](using/functiontodatetime.md)
      + [toDateTimeOnly](using/functiontodatetimeonly.md)
      + [toDecimal](using/functiontodecimal.md)
      + [toDuration](using/functiontoduration.md)
      + [toInteger](using/functiontointeger.md)
      + [toString](using/functiontostring.md)
      + [toTimeZone](using/functiontotimezone.md)
    + Date {#date}
      + [currentTime​InMillis](using/functioncurrenttimeinmillis.md)
      + [inLastDays](using/functioninlastdays.md)
      + [inLastHours](using/functioninlasthours.md)
      + [inLastMonths](using/functioninlastmonths.md)
      + [inLastYears](using/functioninlastyears.md)
      + [inNextDays](using/functioninnextdays.md)
      + [inNextHours](using/functioninnexthours.md)
      + [inNextMonths](using/functioninnextmonths.md)
      + [inNextYears](using/functioninnextyears.md)
      + [now](using/functionnow.md)
      + [nowWithDelta](using/functionnowwithdelta.md)
      + [setHours](using/functionsethours.md)
      + [setDays](using/functionsetdays.md)
      + [updateTimeZone](using/functionupdatetimezone.md)
    + List {#list}
      + [distinct](using/functiondistinct.md)
      + [distinctWithNull](using/functiondistinctwithnull.md)
      + [in](using/functionin.md)
      + [listSize](using/functionlistsize.md)
      + [serializeList](using/functionserializelist.md)
      + [sort](using/functionsort.md)
    + Math {#math}
      + [random](using/functionrandom.md)
      + [round](using/functionround.md)
    + String {#string}
      + [concat](using/functionconcat.md)
      + [contain](using/functioncontain.md)
      + [containWithIgnoreCase](using/functioncontainwithignorecase.md)
      + [endWith](using/functionendwith.md)
      + [endWithIgnorecase](using/functionendwithignorecase.md)
      + [equalIgnoreCase](using/functionequalignorecase.md)
      + [indexOf](using/functionindexof.md)
      + [isEmpty](using/functionisempty.md)
      + [isNotEmpty](using/functionisnotempty.md)
      + [lastIndexOf](using/functionlastindexof.md)
      + [length](using/functionlength.md)
      + [lower](using/functionlower.md)
      + [matchRegExp](using/functionmatchregexp.md)
      + [notEqualIgnoreCase](using/functionnotequalignorecase.md)
      + [replace](using/functionreplace.md)
      + [replaceAll](using/functionreplaceall.md)
      + [startWith](using/functionstartwith.md)
      + [startWithIgnoreCase](using/functionstartwithignorecase.md)
      + [substr](using/functionsubstr.md)
      + [trim](using/functiontrim.md)
      + [upper](using/functionupper.md)
      + [uuid](using/functionuuid.md)
+ Building your Journeys reports{#journey-reports}
  + [Building your Journeys reports](using/reporting.md)
  + [Creating your Journeys reports](using/reportingcreating.md)
  + [Dimensions and metrics available for Journeys](using/reportingdimensions.md)
+ Journeys use cases{#use-cases-journeys}
  + Simple use case{#use-case-simple}
    + [Simple use case](using/uc1intro.md)
    + [Pre-requisites](using/uc1prereq.md)
    + [Configuring the event](using/uc1event.md)
    + [Configuring the data source](using/uc1ds.md)
    + [Building the journey](using/uc1journey.md)
  + Advanced use case{#use-case-advanced}
    + [Advanced use case](using/uc2intro.md)
    + [Pre-requisites](using/uc2prereq.md)
    + [Configuring the events](using/uc2event.md)
    + [Configuring the data source](using/uc2ds.md)
    + [Building the journey](using/uc2journey.md)
  + [Leveraging fatigue scores](using/uc3.md)
  