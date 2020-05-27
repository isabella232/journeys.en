---
title: journeysteps events common fields
description: journeysteps events common fields
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

# journeysteps events common fields {#sharing-common-fields}

The following fields are the ones deduced from the usecases  (see "Use Cases section)  representing the different patterns in a journey:
						
#### entrance

Indicate if the user has entered the journey. If not present, assuming that the value is false

Type: boolean

Values: true/false

#### reentrance

Indicate if the user has reentered the journey with the same instance. If not present, assuming that the value is false	

Type: boolean

Values: true/false

#### instanceEnded

Indicate if the instance is ended (sucessfully or not)

Type: boolean

#### eventId

Event id in processing, for the step processing. If the event is an external one, the value is its eventId. If the event is an internal one, the value is the internal eventId (such as scheduledNotificationReceived, executedAction, ...)

Type: string

#### nodeId

client node id (from the canvas). It may allow in the future to link stepEvents to journey version canvas

Type: string

#### stepId

Unique id of the step that is currently in processing

Type: strinG

#### stepName

Name of the step that is currently in processing

Type: string							

#### stepType

Type of the step

Type: string

Possible values:

* Condition										
* Action										
* Scheduler										
* Timer										

#### stepStatus

Status of the step, representing in which shape the step is, when its processing has been done (and the step event fired).

Type: string

The status can be:

* ended: the step has no transition and its processing has ended successfully
* error: the step processing has raised an error
* transitions: the step is waiting for an event to transition to another step
* capped: the step has failed on a capping error, raised during an action or enrichment
* timedout: the step has failed on a timeout error, raised during an action or enrichment
* instanceTimedout: the step has stopped its processing, because the instance has reached its timeout
						
#### journeyId

ID of the journey

Type: strinG

#### journeyVersionId

ID of the journey version. This id represents the identity reference to the journey, in case of the journeyStepEvent

Type: string

#### journeyVersionName

Name of the journey version

Type: string

#### journeyVersion

Version of the journey version		

Type: string						

#### instanceId

Internal ID of the journey instance

Type: string						

#### externalKey

External key extracted from the event to process it

Type: string

#### parentStepId

Step ID of the parent of the current processed step in the instance

Type: string

#### parentStepName

Step name of the parent of the current step.

Type: string

#### parentTransitionId

Id of the transition which has brought the instance to the processed step

Type: string

#### parentTransitionName

Name of the transition which has brought the instance to the processed step

Type: string

#### inTest

Whether this journey is in test mode or not

Type: boolen

#### processingTime

total time in millis from the instance step entrance to the end of the processing

Type: long

#### instanceType

indicate the instance type, if it is batch or unitary

Type: string

Values: batch/unitary
							
#### recurrenceIndex

index of the recurrence if the journey is batch and recurring (first run has recurrenceIndex = 1)

Type: long

#### isBatchToUnitary

indicates if this unitary instance has been triggered from a batch instance

Type: boolean

#### batchExternalKey

if the instance has been triggered from a batch instance, batch external key

Type: string

#### batchInstanceId

if the instance has been triggered from a batch instance, batch instance id

Type: string

#### batchUnitaryBranchId

if the instance has been triggered from a batch instance, unitary branch id

Type: string
