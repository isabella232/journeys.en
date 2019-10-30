---
product: Journeys
audience: end-user
user-guide-title: Journeys Help
index: n
---

# Journeys Help {#using}

+ [Product documentation](journeys-home.md)
+ Starting with Journeys {#starting-with-journeys}
  + [About Journeys](using/about/intro.md)
  + [User Process](using/about/aboutprocess.md)
  + [The Journeys' interface](using/about/aboutinterface.md)
  + [Ending a journey](using/about/aboutending.md)
  + [Managing your users' access to Journeys](using/about/usermanagement.md)
  + [Troubleshooting](using/about/troubleshooting.md)
+ About events {#events-journeys}
  + [Configuring an event](using/event/event.md)
  + [Defining the payload fields](using/event/eventpayload.md)
  + [Selecting the namespace](using/event/eventnamespace.md)
  + [Defining the event key](using/event/eventkey.md)
  + [Adding a condition](using/event/eventcondition.md)
  + [Previewing the payload](using/event/eventpayloadpreview.md)
  + [Additional steps to receive events](using/event/eventsteps.md)
+ About datasources {#data-source-journeys}
  + [Configuring a datasource](using/datasource/ds.md)
  + [Defining the payload fields](using/datasource/dsfield.md)
  + [Adobe Experience Platform data source](using/datasource/dsplatform.md)
  + [External data sources](using/datasource/dsexternal.md)
+ About custom actions {#custom-action-journeys}
  + [Configuring a custom action](using/custom-action/custom.md)
  + [Custom action limitations](using/custom-action/customlimitations.md)
  + [URL configuration](using/custom-action/customurl.md)
  + [Configuring the authentication](using/custom-action/customauthentication.md)
  + [Defining the message parameters](using/custom-action/customparameters.md)
+ About building journeys {#building-journeys}
  + [Building a journey](using/building-journeys/journey.md)
  + [The journey designer's interface](using/building-journeys/journeyinterface.md)
  + [The journey's properties](using/building-journeys/journeyproperty.md)
  + [Events activities](using/building-journeys/journeyevent.md)
  + [Orchestration activities](using/building-journeys/journeyorchestration.md)
  + [Action activities](using/building-journeys/journeyaction.md)
  + [Testing and publishing the journey](using/building-journeys/journeypublication.md)
  + [Journey versions](using/building-journeys/journeyversions.md)
+ Building advanced conditions {#building-advanced-conditions-journeys}
  + [Building advanced conditions](using/expression/expressionadvanced.md)
  + [Generalities](using/expression/expressiongeneralities.md)
  + [Constants](using/expression/expressionconstants.md)
  + [Field references](using/expression/expressionfields.md)
  + [Operators](using/expression/expressionoperators.md)
  + [Functions](using/expression/expressionfunctions.md)
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
  + [Building your Journeys reports](using/reporting/reporting.md)
  + [Creating your Journeys reports](using/reporting/reportingcreating.md)
  + [Dimensions and metrics available for Journeys](using/reporting/reportingdimensions.md)
+ Use cases{#use-cases-journeys}
  + Simple use case{#use-case-simple}
    + [Introduction](using/usecase/uc1intro.md)
    + [Pre-requisites](using/usecase/uc1prereq.md)
    + [Configuring the event](using/usecase/uc1event.md)
    + [Configuring the data source](using/usecase/uc1ds.md)
    + [Building the journey](using/usecase/uc1journey.md)
  + Advanced use case{#use-case-advanced}
    + [Introduction](using/usecase/uc2intro.md)
    + [Pre-requisites](using/usecase/uc2prereq.md)
    + [Configuring the events](using/usecase/uc2event.md)
    + [Configuring the data source](using/usecase/uc2ds.md)
    + [Building the journey](using/usecase/uc2journey.md)
  + [Leveraging fatigue scores](using/usecase/uc3.md)
  