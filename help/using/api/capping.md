---
title: Capping API description
description: Learn more about the Capping API.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
---

# Capping API

## Introduction

Journey Orchestration's APIs support 5000 event/seconds but some external systems or API could not have an equivalent throughput. That's why Journey Orchestration comes with a dedicated feature called Capping API to monitor and limit the rate that we impose to external systems.
For example, ...système de réservation pour hotel, il scale moins donc pour le protéger on place un seuil à 2000/s 

During a datasource configuration, you will define a connection to a system to retrieve additional information that will be used in your journeys, or for an action definition, you will configure connection of a third-party system to send messages or API calls. Each time an API call is performed by Journey, the capping API is queryied, the call comes through the API engine. If there is a limit defined, the call is rejected and the external system will not be overloaded.

To learn more on action or datasource configuration, see [About actions](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) or [About data sources](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Resources
The Journey Orchestration Capping API is described within a Swagger file. => Link 

To use this API with your Journey Orchestration instance, you need to use the AdobeIO Console. You can start by following this [Getting Started with Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) and then use the sections in this page.

## Authentification

### Setting up API access

Journey Orchestration API access is set up through the steps below. Each of these steps is detailed in the [Adobe IO documentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>To manage certificates in Adobe IO, make sure you have <b>System administrator</b> rights on the organization or a <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">developer account</a> in the Admin console.

1. **Check you have a digital certificate**, or create one if necessary. The public and private keys provided with the certificate are needed in the following steps.
1. **Create a new integration to Journey Orchestration Service** in Adobe IO and configure it. The product profile access is needed for Journey Orchestration and Adobe Experience Platform. Your credentials will then be generated (API Key, Client secret...).
1. **Create a JSON Web Token (JWT)** from the credentials previously generated and sign it with your private key. The JWT encodes all of the identity and security information that is needed by Adobe to verify your identity and grant you access to the API. This step is detailed in this [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Exchange your JWT for an Access Token** through a POST request. This Access Token will have to be used in each header of your API requests.

To establish a secure service-to-service Adobe I/O API session, every request to an Adobe service must include in the Authorization header the information below.

```

curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'X-Api-Key: <API_KEY>' \
 -H 'X-gw-ims-org-id: <ORGANIZATION>'

```

* **&lt;ORGANIZATION&gt;**: This is your personal ORGANIZATION ID, one ORGANIZATION ID is provided by Adobe for each of your instances :

    * &lt;ORGANIZATION&gt; : your production instance

    To obtain your ORGANIZATION ID value, refer to your administrator or your Adobe technical contact. You can also retrieve it into Adobe I/O when creating a new integration, in the licenses list (see the <a href="https://www.adobe.io/authentication.html">Adobe IO documentation</a>).

* **<ACCESS_TOKEN>**: Your personal access token, that was retrieved when exchanging your JWT through a POST request.

* **<API_KEY>**: your personal API Key. It is provided in Adobe I/O after creating a new integration to Journey Orchestration Service.



## Capping API description

The Capping API helps you to create, configure and monitor your capping configurations.

| Method  | Path   | Description   |
|---|---|---|
| POST | list/endpointConfigs  | Get a list of the endpoint capping configurations |
| POST | /endpointConfigs  | Create an endpoint capping configuration |
| POST | /endpointConfigs/{uid}/deploy  | Deploy an endpoint capping configuration |
| POST | /endpointConfigs/{uid}/undeploy  | Undeploy an endpoint capping configuration |
| POST | /endpointConfigs/{uid}/canDeploy  | Check if an endpoint capping configuration can be deployed or not |
| PUT | /endpointConfigs/{uid} | Update an endpoint capping configuration |
| GET | /endpointConfigs/{uid} | Retrieve an endpoint capping configuration |
| DELETE | /endpointConfigs/{uid} | Delete an enpoint capping configuration |

When a configuration is created or updated, a check is automatically performed to guarantee the syntax and the integrity of the payload.
If some problems occur, the operation returns warning or errors to help you to correct the configuration.



## Endpoint configuration

Here is the basic structure of an endpoint configuration:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint> (if no value, 0 or <1 = warning, no max connections defined)
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Example:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## Warning and errors 

When a **canDeploy** method is called, the process validates the configuration and returns the validation status identified by its Unique ID, either:

```

"ok" or "error"

```

The potential errors are:

* **ERR_ENDPOINTCONFIG_100**: capping config: missing or invalid url
* **ERR_ENDPOINTCONFIG_101**: capping config: malformed url
* **ERR_ENDPOINTCONFIG_102**: capping config: malformed url: wildchar in url not allowed in host:port
* **ERR_ENDPOINTCONFIG_103**: capping config: missing HTTP methods
* **ERR_ENDPOINTCONFIG_104**: capping config: no call rating defined
* **ERR_ENDPOINTCONFIG_107**: capping config: invalid max calls count (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: invalid max calls count (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config: can't create endpoint config: invalid payload
* **ERR_ENDPOINTCONFIG_112**: capping config: can't create endpoint config: expecting a JSON payload
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: invalid service name '<given value>': must be 'dataSource' or 'action'


The potential warning is:

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limitation by default



## Use-cases

In this section, you will find the five main use-cases that you can perform to manage your capping configuration in Journey Orchestration.

To help you in your testing and configuration, a Postman environemennt annd collection are available here:

Once downloaded and uploaded into Postman, you need to add two variables: `{JO_HOST}` and `{Base_Path}`.
* `{JO_HOST}` :
* `{Base_Path}` :



Use-Case n°1: creation and deployment of a new capping configuration

1. list
1. create
1. candeploy
1. deploy

Use-Case n°2: update and deploy a capping configuration not deployed yet

1. list
1. get
1. update
1. candeploy
1. deploy

Use-Case n°3: undeploy and delete a deployed capping configuration

1. list
1. undeploy
1. delete

Use-Case n°4: delete a deployed configuration (will undeploy and delete the config)

1. list
1. delete, with forceDelete param

Use-Case n°5: update a capping configuration already deployed

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy




(Si l'action comporte une phase d'authentication et une phase d'écriture/lecture, alors on peut définir un capping différent sur l'auth et sur la phase de lecture/écriture sur le système externe.)












