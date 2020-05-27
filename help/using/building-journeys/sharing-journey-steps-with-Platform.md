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

# Sharing journey steps with Platform{#sharing-journey-steps}

This feature automatically creates schemas and streams datasets to Adobe Experience Platform for each step of an individual in a journey. This data can then be used for analysis via a business intelligence tool.

It is activated automatically for all customers.

The following schemas are created:

* Journey Step Profile Event schema for Journey Orchestration – Experience Events for steps taken in a Journey along with an Identity Map to be used for mapping to an individual Journey Participant.
* Journey Step Event schema for Journey Orchestration – Journey step event that is tied to a Journey Metadata.
* Journey schema with Journey Fields for Journey Orchestration – Journey Metadata to describe Journeys.

The following datasets are passed:

* Journey Step Profile Event schema for Journey Orchestration
* Journey Step Events
* Journeys

journeyStep events common fields
						
## entrance

Indicate if the user has entered the journey. If not present, assuming that the value is false

Type: boolean

Values: true/false

### reentrance** (Boolean)

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