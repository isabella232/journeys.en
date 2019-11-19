---
title: Managing your users' access to Journey Orchestration
description: 
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: n
internal: n
snippet: y
---

# Managing your users' access to Journey Orchestration{#concept_rfj_wpt_52b}

Define your users' access levels using security groups and roles.

Permissions can be given to users of your instance to authorize or deny access to certain functionalities or objects in the interface. These permissions can be divided into three concepts:

* **Organizational units**: objects and users are linked to organizational units which allow a hierarchical structure and a filtered view of your interface. For more on how to create and manage organizational units, refer to the [Adobe Campaign](https://helpx.adobe.com/campaign/standard/administration/using/organizational-and-geographical-units.html) documentation.
* **Roles**: set of rights to define what users can or cannot work on in the interface. These roles are assigned through security groups.
* **Security groups**: set of users that share the same roles and rights within an organization.

These concepts can be found under the advanced menu **Administration > Users & Security**.

**Roles**

The following out-of-the box roles allow you to give users permission to perform specific tasks and to restrict access to some functionalities. They are only available in Adobe Campaign Standard by selecting **Administration** > **Users & security** > **Roles**.

The set of roles assigned to a security group will define the user's access to the different features.

![](../assets/user_management.png)

The following out-of-the-box roles are specific and unique to users that need to use Journey Orchestration:

* **Manage and execute journeys**
* **Read journeys**
* **Manage events, resources and keys**
* **Read events and resources**
* **Manage reports**
* **Read reports**

You can find below the compatibility between roles and Journey Orchestration's different functionalities:

![](../assets/user_management_3.png)

Additional roles linked to Adobe Campaign Standard use such as prepare deliveries, generic import, etc. are also available. For more on this refer to [Adobe Campaign](https://helpx.adobe.com/campaign/standard/administration/using/list-of-roles.html) documentation.

**Security group**

Security groups are assigned to a set of users that share the same roles and rights within your organization.

![](../assets/user_management_2.png)

You can create your own security group with the different roles needed or you can assign one of the following out-of-the-box security groups to your users:

*   **Limited Access User**: User with read only access to journeys, events and reports. This security group includes the following roles:
    *   Read journeys
    *   Read events and resources
    *   Read reports
*   **Administrators**: User with access to the administration menus with the possibility to manage journeys, events and reports. This security group includes the following roles:
    *   Administration
    *   Data model
    *   Generic import
    *   Export
    *   File access
    *   Prepare deliveries
    *   Start deliveries
    *   Workflow
    *   Manage and execute journeys
    *   Manage events, resources, and keys
    *   Manage reports

    >[!NOTE]
    >
    >**Administrators** is the only security group allowing creation, edition and publication of transactional messaging which allows message sending for Journey Orchestration.

*   **Standard User**: User with basics access to Adobe Campaign with the possibility to manage journeys. This security group includes the following roles:
    *   Prepare deliveries
    *   Start deliveries
    *   Workflow
    *   Manage and execute journeys
    *   Read events and resources
    *   Manage reports

Other security groups linked to Adobe Campaign Standard roles are available. For more on this refer to [Adobe Campaign](https://helpx.adobe.com/campaign/standard/administration/using/managing-groups-and-users.html) documentation.