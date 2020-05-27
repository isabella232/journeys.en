---
title: journeyStep events data fetch fields
description: journeyStep events data fetch fields
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

# journeyStep events data fetch fields {#sharing-fetch-fields}

This mixin will be shared by the journeyStepEvent and journeyStepProfileEvent.

During a step processing, we can have N data fetch on field groups AEP or custom. We have tried not to surface the field group notion and granularity, to capture:

* global data fetch time on all potential field groups
* global error and code, to ease aggregation computation instead of dealing with custom and AEP properties
* global data fetch count
* same information, but at source type granularity
						
#### fetchTotalTime 

total amount of time spent in data fetch in millis during the step processing

Type: long

#### fetchTypeInError

define if the fetch in error is on the platform or on a custom data source

Type: string

Values: 
* aep
* custom
  
#### fetchError

Type of error that happens when the data fetch is processed.

Type: string

Values: 
* http
* capping
* timedout
* error
  
#### fetchErrorCode  
  
Code for fetch error. Present if the error has a code, such as an HTTP one. For instance, if the actionExecError is http, the code 404 represents the HTTP 404 error

Type: string

#### fetchOrigError
  
A timeout can occur, in two cases:

* at the first attempt to execute the action. In this case, the execution is not finished, so there is no underlying error
* on a retry: in this case, the actionExecOrigError/actionExecOrigErrorCode describes the error encountered on the attempt before the retry

For instance, let's say that we are trying to fetch data from UPS and we get a HTTP 500 error at the first attempt. We will retry the fetch, but the duration of the 2 attempts exceeds the timeout. Then the action execution is tagged as timedout. In order not to loose the fact that this timedout has been raised because of a HTTP 500, the action part will look like:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Type: string

#### fetchOrigErrorCode

Type: string
  
#### fetchCount

How many times the data is fetched, regardless of the type of source (AEP, custom)

Type: long

#### fetchAepTotalTime
The total amount of time taken to fetch the data from Data Platform in millis. Remark: this time is computed from the time the engine sends the enrichment event to the enrichment service and receive the response

Type: long

#### fetchAepCount

How many times the data is fetched from Platform

Type: long

#### fetchCustomTotalTime

Time to fetch the custom data in millis. Remark: this time is computed from the time the engine sends the enrichment event to the enrichment service and receive the response

Type: long

#### fetchCustomCount

How many times the custom data is fetched from external systems

Type: long
