---
title: Operators
seo-title: Operators
description: Operators
seo-description: Learn about operators in journeys' advanced conditions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: y
internal: n
snippet: y
---


# Operators {#concept_wd5_pj5_dgb}

There are two kinds of operators: unary operators and binary operators. There are left-hand unary operators and right-hand unary operators.

```

// left-hand unary operators
&lt;operator> &lt;operand> // operand is an expression
not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

// right-hand unary operators
&lt;operand> &lt;operator> // operand is an expression
@{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

 
// binary operators
&lt;operand1> &lt;operator> &lt;operand2>
(@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or 
(@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")

```

Here is the list of supported operators:

|Category|Operator|Literal Expression|Example|
|--- |--- |--- |--- |
|Logical|and|`<expression1> and <expression2>`Both `<expression1>` and `<expression2>` must be boolean. The result is boolean.|`3.14 > 2 and 3.15 < 1`|
|Logical|or|`<expression1> or <expression2>`Both `<expression1> and <expression2>` must be boolean. The result is boolean.|3.14 > 2 or 3.15 < 1|
|Logical|not|`not <expression>``<expression>` must be boolean. The result is boolean.|not 3.15 < 1|
|Comparison|is null|`<expression> is null`The result is boolean.Note that null means the expression has no evaluated value.|`@{BarBeacon.location} is null`|
|Comparison|is not null|`<expression> is not null`The result is boolean.Note that null means the expression has no evaluated value.|@{BarBeacon.location} is not null|
|Comparison|has null|`<expression> has null``<expression>` must be a list. The result is boolean.Useful to identify that a list contains at least one null value.|`["foo", "bar", null] has null`returns true`["foo", "bar", ""] has null`returns false because "" is not considered as null.|
|Comparison|==|`<expression1> == <expression2>`Both `<expression1>` and `<expression2>` must have the same data type. The result is boolean.|`3.14 == 42``"foo" == "bar"`|
|Comparison|!=|`<expression1> != <expression2>` Both `<expression1>` and `<expression2>` must have the same data type. The result is boolean.|`3.14 != 42``"foo" != "bar"`|
|Comparison|>|`<expression1> > <expression2>`Datetime can be compared with Datetime.Datetimeonly can be compared with Datetimeonly.Both integer or decimal can be compared with both integer or decimal.Any other combination is forbidden.The result is boolean.|3.14 > 42|
|Comparison|>=|`<expression1> >= <expression2>`Datetime can be compared with Datetime.Datetimeonly can be compared with Datetimeonly.Both integer or decimal can be compared with both integer or decimal.Any other combination is forbidden.The result is boolean.|42 >= 3.14|
|Comparison|<|`<expression1> < <expression2>`Datetime can be compared with Datetime.Datetimeonly can be compared with Datetimeonly.Both integer or decimal can be compared with both integer or decimal.Any other combination is forbidden.The result is boolean.|42 < 3.14|
|Comparison|<=|`<expression1> <= <expression2>`Datetime can be compared with Datetime.Datetimeonly can be compared with Datetimeonly.Both integer or decimal can be compared with both integer or decimal.Any other combination is forbidden.The result is boolean.|42 <= 3.14|
|Arithmetic|+|`<expression1> + <expression2>` Both expressions must be numeric (integer or decimal). The result is also numeric.|`1 + 2`Returns 3|
|Arithmetic|-|`<expression1> - <expression2>` Both expressions must be numeric (integer or decimal). The result is also numeric.|`2 - 1`Returns 1|
|Arithmetic|/|`<expression1> / <expression2>` Both expressions must be numeric (integer or decimal). The result is also numeric. `<expression2>` must not be equal to 0 (returns 0).|`4 / 2`Returns 2|
|Arithmetic|*|`<expression1> * <expression2>` Both expressions must be numeric (integer or decimal). The result is also numeric.|`3 * 4`Returns 12|
|Arithmetic|%|`<expression1> % <expression2>` Both expressions must be numeric (integer or decimal). The result is also numeric.|`3 % 2`Returns 1|
|Math|is numeric|`<expression> is numeric`The type of the expression is integer or decimal.|@{BarBeacon.location} is numeric.|
|Math|is integer|`<expression> is integer`The type of the expression is integer.|@{BarBeacon.location} is integer|
|Math|is decimal|`<expression> is decimal`The type of the expression is decimal.|@{BarBeacon.location} is decimal|
|String|+|`<string> + <expression>``<expression> + <string>`It concatenates two expressions or more. The first expression must be a string. The other expressions can be of any type. The result is a string.|`"the current time is " + (now()) Returns  "the current time is 2019-09-23T09:30:06.693Z"`(now()) + " is the current time"Returns 2019-09-23T09:30:06.693Z is the current time`"a" + "b" + "c" + 1234 Returns abc1234|
|Date|+|`<expression + <duration>`Append a duration to a dateTime, a dateTimeOnly or a duration.|`toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")`Returns 2011-12-03T15:30:30Z`toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")`Returns 2011-12-03T15:30:30`now() + toDuration("PT1H")`Returns a dateTime (with UTC timezone) one hour later from current time`toDuration("PT1H") + toDuration("PT1H")`Returns returns PT2H|
