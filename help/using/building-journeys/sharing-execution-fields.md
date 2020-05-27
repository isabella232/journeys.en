---
title: journeyStep events action execution fields
description: journeyStep events action execution fields
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

# journeyStep events action execution fields {#sharing-execution-fields}

This mixin will be shared by the journeyStepEvent and journeyStepProfileEvent.

If the step has an action to be processed, those fields will be added to the event payload. 
						
#### actionId

Id of the action that is being executed.

Type: string

#### actionName

Name of the action. If no name has been set, the stepName will be taken.

Type: string

#### actionType

Type of the action.

Type: string

#### actionParameterized

Indicates if the action is parameterized or not.

Type: boolean

#### actionExecTime

The amount of time (in millis) taken to execute a current action.

Type: long

#### actionExecError

Type of error that happens when the action is called.

Type: string

Values:
* http
* capping
* timeout
* error
	
#### actionExecErrorCode

Code for action execution error. Present if the error has a code, such as an HTTP one. For instance, if the actionExecError is http, the code 404 represents the HTTP 404 error.

Type: string

#### actionExecOrigError
	
A timeout can occur, in two cases:

* at the first attempt an action is executed. In this case, the execution is not finished, so there is no underlying error
* on a retry: in this case, the actionExecOrigError/actionExecOrigErrorCode describes the error encountered on the attempt before the retry.

For instance, an email is being sent and an HTTP 500 error is returned at the first attempt. The fetch is retried, but the duration of the 2 attempts exceeds the timeout. Then the action execution is tagged as timedout. The action part will look like:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Type: string

#### actionExecOrigErrorCode
	
Error code of the actionExecOrigError.

Type: string

#### actionBusinessType	

Indicates the type of action. 

Values:

* builtin
 * ACS Email
 * ACS SMS
 * ACS Push
* customer
 * Epsilon
 * ...

Type: string
	
#### actionSchedulerCount

Count of scheduler notification requests sent to the scheduler service during the step processing.

Type: long
