---
title: Field references
description: Learn about field references in advanced conditions
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


# Field references {#concept_fkj_ll5_dgb}

A field reference can be attached to an event or a field group. The only meaningful information is the name of the field and its path. 

If you're using special characters in a field, you need to use double quotes. Here are the cases when quotes are needed:

* the field starts with numerical characters
* the field starts with the "-" character
* the field contains anything other than: _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

For example if your field is _3h_: _#{OpenWeather.weatherData.rain.'3h'} > 0_


```

// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatformDataSource.ProfileFieldGroup.Profile.personalEmail.address}

```


In the expression, event fields are referenced with "@" and data source fields are referenced with "#".

A syntax color is used to visually distinguish events fields (green) from field groups (blue).

**Default values for field references**

A default value can be associated to a field name. the syntax is as follows:


```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatformDataSource.ProfileFieldGroup.Profile.personalEmail.address, defaultValue: "example@adobe.com"}
```


>[!NOTE]
>
>The type of the field and the default value must be the same. For example, `@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} will be invalid because the default value is an integer whereas the expected value should be a string.

**Parameter values of a data source (data source dynamic values)**

If you select a field from an external data source requiring a parameter to be called, a new tab appears on the right to let you specify this parameter. See [Using the advanced expression editor](../expression/expressionadvanced.md#concept_uyj_trt_52b).

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. A parameter can be any valid expression even from another data source that also include another parameter.

>[!NOTE]
>
>When you define the parameter values in the expression, the tab on the right disappears.

Use the following syntax:


```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```


* **`<params-1-name>`**: exact name of the first parameter from the data source.
* **`<params-1-value>`**: the value of the first parameter. It can be any valid expression.

Example:


```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```

