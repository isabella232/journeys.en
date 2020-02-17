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

## Q1 Release - february 2019 {#q1-release---february-2019}

**Timezone management**

Timezones are now managed at journey level. Two parameters have been added in the journey properties:

![](../assets/rn-timezone.png)

* The **Timezone** drop-down allows you to select a specific timezone. By default, the browser's timezone is used. 

* The **Profile Timezone** checkbox allows you to use the Experience Platform Profile timezone of the person entering the journey, if available. If not, the timezone defined in the drop-down will be used. This feature is not compatible with journeys with no namespace.

**Contextual Help**

A contextual help function is now available across the different Journey Orchestration screens. This means that, in a single click, you can directly access the documentation on the functionality that you are currently using. 

To display contextual help, click the ‘i’ icon in the upper-right corner of the screen. 

For now, this feature is avaible in the Home, Data Sources, Events and Actions list screens.

**Other changes**

* In test mode, a new parameter allows you to define the time peafiner.  time wait activities can last. This allows you to access the test results quickly.

* In test mode, you can now trigger all events of the journey. 


* a new parameter allows you to define the time peafiner.  time wait activities can last. This allows you to access the test results quickly.

* Journeys Orchestration is now available in EMEA.

* New icon in palette, to display r notunavailble items. sans namespace. par default .

* canvas, deconnection, petite icone, qui dit disconnected node.

* short cut C ttes les listes

* palette UI, icone de search resultats

* Pouvoir capper les call a des APIS externes (data sources ou actions). marque n'accepte que 500 calls par seconde, elle pourra mettre un capping a 500 calls seconds qui evite de surcharger system de loyalty tiers

* logs du test log. Avant status = error. quand on appalle systemtieds. Possibilityé de voir code erreur phrase qu'à renvoyé le systeme. -> ds un test en cas d'erreur, systeme tiers, error code, error response. 

* stopped delete journey

* journey: version 1 il te met si latest

1er mars.


## GA Release - December 2019 {#ga-release---december-2019}

Journey Orchestration is now GA. 

Build real-time orchestration use cases leveraging contextual data stored in events or data sources.

Journey Orchestration allows real-time orchestration powered by contextual data from events, information from the Adobe Experience Platform, or data from third-party API services. The application determines in multistep flows called journeys the next best actions specific to the consumer, based on their profile and behaviors. This comprises both the optimal timing, as well as the type of action, such as sending the consumer a push notification via Adobe Campaign Standard transactional messaging capabilities (requires Adobe Campaign Standard) or the notification of a third-party system. These decisions are made based on rules and Sensei scores.

[Learn more](../action/working-with-adobe-campaign.md) on Journey Orchestration.

Additional resources:

* [Tutorials](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)