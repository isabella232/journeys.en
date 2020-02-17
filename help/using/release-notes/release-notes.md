---
title: Release Notes
description: Learn about release notes
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

# Release Notes {#release-notes}

This page lists all the new features and improvements for Journey Orchestration.
You can also consult the [Documentation Updates](../release-notes/documentation-updates.md).

## Q1 Release - February 2019 {#q1-release---february-2019}

**What's new?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Timezone management</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
   	<p>Timezones are now managed at journey level. Two parameters have been added in the journey properties:</p>
   	<img src="../assets/rn-timezone.png"/>
   	<ul>
    <li>The <strong>Timezone</strong> drop-down allows you to select a specific timezone. By default, the browser's timezone is used. </li>
    <li>The <strong>Profile Timezone</strong> checkbox allows you to use the Experience Platform Profile timezone of the person entering the journey, if available. If not, the timezone defined in the drop-down is be used. This feature is not compatible with journeys with no namespace.</li>
    </ul>
    <p>For more information, refer to the <a href="../building-journeys/building-journeys/changing-properties.md">detailed documentation</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Contextual Help</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>A contextual help is now available across the different Journey Orchestration screens. This allows to view a quick description of the current functionality and access related articles and videos. </p>
   	<p>To display the contextual help, click the <img src="../assets/icon-context.png"/> icon in the upper-right corner of the screen. </p>
   	   	<img src="../assets/rn-context.png"/>
    <p>For now, this feature is available in the <strong>Home</strong>, <strong>Data Sources</strong>, <strong>Events</strong> and <strong>Actions</strong> list screens.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Test mode enhancements</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Two enhancements have been made to the test mode:</p>
    <ul>
    <li>When your journey uses several events, you can now trigger the firing of each events using a drop-down, in the <strong>Event configuration</strong> screen of the test mode.</li>
    <li>When one ore more <strong>Wait</strong> activities are used in a journey, you can now define the time that each of these activities will last in test mode. The default time is 10 seconds. You can change this using the <strong>Wait time in test</strong> parameter, in the bottom left corner. </li>
    </ul>
        <img src="../assets/rn-test.png"/>
   </td> 
  </tr> 
 </tbody> 
</table>

**Other improvements**

Journeys Orchestration is now available in **EMEA**.

The journey **palette**, on the left side of the journey canvas has been enhanced:

* A new icon, in the top left corner, allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. By default, unavailable items are hidden.

* When using the **Search** field, we now display the number of results for each category.

* The display of the categories has been improved. They now unfold from the top.

In the journey **canvas**, when two activities are disconnected, we now display a warning message.

The **C** keyboard shortcut is now available in all list screens: journeys, data sources, actions, events.

In the **test logs**, we now display the error code and error response for third-party calls. 

We now allow the **deletion** of stopped journeys. Reports associated to these deleted journeys will not be available.

When there is only one **version** of a journey, we now display the fact that it is the latest version, next to its name. 

## GA Release - December 2019 {#ga-release---december-2019}

Journey Orchestration is now GA. 

Build real-time orchestration use cases leveraging contextual data stored in events or data sources.

Journey Orchestration allows real-time orchestration powered by contextual data from events, information from the Adobe Experience Platform, or data from third-party API services. The application determines in multistep flows called journeys the next best actions specific to the consumer, based on their profile and behaviors. This comprises both the optimal timing, as well as the type of action, such as sending the consumer a push notification via Adobe Campaign Standard transactional messaging capabilities (requires Adobe Campaign Standard) or the notification of a third-party system. These decisions are made based on rules and Sensei scores.

[Learn more](../action/working-with-adobe-campaign.md) on Journey Orchestration.

Additional resources:

* [Tutorials](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)