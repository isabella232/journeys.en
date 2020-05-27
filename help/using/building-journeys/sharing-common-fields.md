---
title: Sharing journey steps with Platform
description: Sharing journey steps with Platform
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

# Journey steps event common fields {#sharing-common-fields}

This mixin will be shared by the journeyStepEvent and journeyStepProfileEvent.

The following table shows the list of fields that will be sent to Adobe Data Platform from Voyager.  We went through all the use cases shown below and came up with the list of fields that we need to send it to Adobe Data Platform.  There are some common fields that will be sent for every step that is processed in a journey and some specific set of fields for custom actions and enrichments.

Some of those fields are only present in specific processing patterns (action execution, data fetch, ...). We want to limit the size of events, not to put any useless info contextually.

The following fields are the ones deduced from the usecases  (see "Use Cases section)  representing the different patterns in a journey:
						
#### entrance

Indicate if the user has entered the journey. If not present, assuming that the value is false

Type: boolean

Values: true/false

#### reentrance (Boolean)

true/false

Indicate if the user has reentered the journey with the same instance. If not present, assuming that the value is false							
**instanceEnded** (Boolean)

Indicate if the instance is ended (sucessfully or not)					

**eventId** (String)

Event id in processing, for the step processing. If the event is an external one, the value is its eventId. If the event is an internal one, the value is the internal eventId (such as scheduledNotificationReceived, executedAction, ...)					
**nodeId** (String)

client node id (from the canvas). It may allow in the future to link stepEvents to journey version canvas								
**stepId** (String)

Unique id of the step that is currently in processing					

**stepName** (String)

Name of the step that is currently in processing								

**stepType** (String)

Type of the step

Possible values:							
* Condition										
* Action										
* Scheduler										
* Timer										

**stepStatus** (String)

Status of the step, representing in which shape the step is, when its processing has been done (and the step event fired). The status can be:

* ended: the step has no transition and its processing has ended successfully
* error: the step processing has raised an error
* transitions: the step is waiting for an event to transition to another step
* capped: the step has failed on a capping error, raised during an action or enrichment
* timedout: the step has failed on a timeout error, raised during an action or enrichment
* instanceTimedout: the step has stopped its processing, because the instance has reached its timeout
						
**journeyId** (String)

ID of the journey

**journeyVersionId** (String)

ID of the journey version. This id represents the identity reference to the journey, in case of the journeyStepEvent								
**journeyVersionName** (String)

Name of the journey version								

**journeyVersion** (String)

Version of the journey version								

**instanceId** (String)

Internal ID of the journey instance								

**externalKey** (String)

External key extracted from the event to process it

**parentStepId**	String			Step ID of the parent of the current processed step in the instance								
parentStepName	String			Step name of the parent of the current step.								
parentTransitionId	String			Id of the transition which has brought the instance to the processed step								
parentTransitionName	String			Name of the transition which has brought the instance to the processed step								
inTest	Boolean			Whether this journey is in test mode or not								
processingTime	Long			total time in millis from the instance step entrance to the end of the processing								
instanceType	String	batch		indicate the instance type, if it is batch or unitary								
		unitary										
recurrenceIndex	Long			index of the recurrence if the journey is batch and recurring (first run has recurrenceIndex = 1)								
isBatchToUnitary	Boolean			indicates if this unitary instance has been triggered from a batch instance								
batchExternalKey	String			if the instance has been triggered from a batch instance, batch external key								
batchInstanceId	String			if the instance has been triggered from a batch instance, batch instance id								
batchUnitaryBranchId	String			if the instance has been triggered from a batch instance, unitary branch id								