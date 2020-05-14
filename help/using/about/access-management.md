---
title: Access management
description: Learn more on access management
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Access management{#concept_rfj_wpt_52b}

## About access management {#about-access-management}

Journey orchestration allows you to assign a set of rights and sandboxes to your users to define which part of the interface they can access.

They can be managed by Administrators that have access the Admin console. For more information on the Admin console, refer to this documentation.

In the Admin console, you can assign one of the following out-of-the-box product profiles to your users:

*   **[!UICONTROL Limited Access User]**: user with read-only access to journeys and reports. This product profile includes the following rights:
    *   Read journeys
    *   Read reports

*   **[!UICONTROL Administrators]**: user with access to the administration menus with the possibility to manage journeys, events and reports. This product profile includes the following rights:
    *   Manage and execute journeys
    *   Manage events, data sources and actions
    *   Manage reports

    >[!NOTE]
    >
    >**[!UICONTROL Administrators]** is the only product profile which allows creation, edition and publication of transactional messaging (or messaging templates) in Adobe Campaign Standard. This product profile is needed if you use Adobe Campaign Standard to send messages in your journeys.

*   **[!UICONTROL Standard User]**: user with basic access such as journey management. This product profile includes the following rights:
    *   Manage and execute journeys
    *   Manage reports

You can also create your own product profiles if the out-of-the-box profiles are not enough to manage your users.
Users must always be linked to a product profile allowing you to assign them specific build-in rights such as:

*   **[!UICONTROL Read journeys]**
*   **[!UICONTROL Read reports]**
*   **[!UICONTROL Manage events, data sources and actions]**
*   **[!UICONTROL Read events, data sources and actions]**
*   **[!UICONTROL Manage journeys]**
*   **[!UICONTROL Publish journeys]**
*   **[!UICONTROL Manage reports]**

You can find below the compatibility between rights and Journey Orchestration's different functionalities.

![](../assets/journey-permission.png)

## Creating a product profile {#create-product-profile}

Journeys Orchestration allows you to create your own product profiles and assign a set of rights and sandboxes to your users. With product profiles, you can authorize or deny access to certain functionalities or objects in the interface.

For more information on how to create and manage sandboxes, refer to Adobe Experience Platform documentation.

To create a product profile and assign a set of rights and sandboxes:

## Assigning a product profile {#assigning-product-profile}

Product profiles are assigned to a set of users that share the same rights within your organization.
The list of every out-of-the-box product profiles with assigned rights can be found in this section.

To assign a product profile for a user to access Journey Orchestration:

1. In the Admin Console, select **[!UICONTROL Journey orchestration]**.

    ![](../assets/user_management.png)

1. Select the product profile to which your new user will be linked to.

    ![](../assets/user_management_2.png)

1. Click **[!UICONTROL Add user]**.
   
   You can also add your new user to a user group to fine-tune the shared set of permissions. For more on this, refer to this [page](https://helpx.adobe.com/enterprise/using/user-groups.html).

    ![](../assets/user_management_3.png)

1. Type in the email address of your new user then click **[!UICONTROL Save]**.

    ![](../assets/user_management_4.png)

Your user should then receive an email redirecting to your Journey Orchestration instance.