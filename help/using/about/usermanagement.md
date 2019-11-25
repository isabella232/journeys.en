---
title: Access management
description: Learn more on access management
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

# Access management{#concept_rfj_wpt_52b}

## About access management {#about-access-management}

Product profiles are assigned to a set of users that share the same rights within your organization.

In the Admin console, you can assign one of the following out-of-the-box product profiles to your users:

*   **[!UICONTROL Limited Access User]**: User with read only access to journeys and reports. This product profile includes the following rights:
    *   Read journeys
    *   Read reports

*   **[!UICONTROL Administrators]**: User with access to the administration menus with the possibility to manage journeys, events and reports. This product profile includes the following rights:
    *   Manage and execute journeys
    *   Manage events, data sources and action
    *   Manage reports

    >[!NOTE]
    >
    >**[!UICONTROL Administrators]** is the only product profile allowing creation, edition and publication of transactional messaging which allows message sending for Journey Orchestration.

*   **[!UICONTROL Standard User]**: User with basics access such as manage journeys. This product profile includes the following rights:
    *   Manage and execute journeys
    *   Manage reports
    
You can find [](../assets/acs_rights_journeys.pdf) the compatibility between rights and Journey Orchestration's different functionalities.

## Assigning a product profile {#assigning-product-profile}

Product profiles are managed in the Admin console. For more on this, refer to the [Admin Console documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

To assign a product profile for a user to access Journey Orchestration:

1. In the Admin Console, select **[!UICONTROL Journey orchestration]**.

    ![](../assets/user_management.png)

1. Select the product profile to which your new user will be linked to.

    ![](../assets/user_management_2.png)

1. Click **[!UICONTROL Add user]**.
   
   You can also add your new user to a user groups to fine tune the shared set of permissions. For more on this, refer to this [page](https://helpx.adobe.com/enterprise/using/user-groups.html).

    ![](../assets/user_management_3.png)

1. Type in the email address of your new user then click **[!UICONTROL Save]**.

    ![](../assets/user_management_4.png)

Your user should then receive an email redirecting to your Journey orchestration instance.