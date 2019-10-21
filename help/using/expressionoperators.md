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
|Logical|and|`<expression1> and <expression2>`<p>Both `<expression1>` and `<expression2>` must be boolean. The result is boolean.</p>|`3.14 > 2 and 3.15 < 1`|
|Logical|or|`<expression1> or <expression2>`<p>Both `<expression1> and <expression2>` must be boolean. The result is boolean.</p>|3.14 > 2 or 3.15 < 1|
|Logical|not|`not <expression>`<p>`<expression>` must be boolean. The result is boolean.</p>|not 3.15 < 1|
|Comparison|is null|`<expression> is null`<p>The result is boolean.</p><p>Note that null means the expression has no evaluated value.</p>|`@{BarBeacon.location} is null`|
|Comparison|is not null|`<expression> is not null`<p>The result is boolean.</p><p>Note that null means the expression has no evaluated value.</p>|@{BarBeacon.location} is not null|
|Comparison|has null|`<expression> has null`<p>`<expression>` must be a list. The result is boolean.</p><p>Useful to identify that a list contains at least one null value.</p>|`["foo", "bar", null] has null`<p>returns true</p>`["foo", "bar", ""] has null`<p>returns false because "" is not considered as null.</p>|
|Comparison|==|`<expression1> == <expression2>`<p>Both `<expression1>` and `<expression2>` must have the same data type. The result is boolean.</p>|`3.14 == 42``"foo" == "bar"`|
|Comparison|!=|`<expression1> != <expression2>`<p> Both `<expression1>` and `<expression2>` must have the same data type. The result is boolean.</p>|`3.14 != 42``"foo" != "bar"`|
|Comparison|>|`<expression1> > <expression2>`<p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p>|3.14 > 42|
|Comparison|>=|`<expression1> >= <expression2>`<p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p>|42 >= 3.14|
|Comparison|<|`<expression1> < <expression2>`<p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p>|42 < 3.14|
|Comparison|<=|`<expression1> <= <expression2>`<p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p>|42 <= 3.14|
|Arithmetic|+|`<expression1> + <expression2>`<p> Both expressions must be numeric (integer or decimal). The result is also numeric.</p>|`1 + 2`<p>Returns 3</p>|
|Arithmetic|-|`<expression1> - <expression2>`<p> Both expressions must be numeric (integer or decimal). The result is also numeric.</p>|`2 - 1`<p>Returns 1</p>|
|Arithmetic|/|`<expression1> / <expression2>`<p> Both expressions must be numeric (integer or decimal). The result is also numeric.</p> <expression2> must not be equal to 0 (returns 0).|`4 / 2`<p>Returns 2</p>|
|Arithmetic|*|`<expression1> * <expression2>`<p> Both expressions must be numeric (integer or decimal). The result is also numeric.</p>|`3 * 4`<p>Returns 12</p>|
|Arithmetic|%|`<expression1> % <expression2>`<p> Both expressions must be numeric (integer or decimal). The result is also numeric.</p>|`3 % 2`<p>Returns 1</p>|
|Math|is numeric|`<expression> is numeric`<p>The type of the expression is integer or decimal.</p>|@{BarBeacon.location} is numeric.|
|Math|is integer|`<expression> is integer`<p>The type of the expression is integer.</p>|@{BarBeacon.location} is integer|
|Math|is decimal|`<expression> is decimal`<p>The type of the expression is decimal.</p>|@{BarBeacon.location} is decimal|
|String|+|<p>`<string> + <expression>`</p><p>`<expression> + <string>`</p><p>It concatenates two expressions or more. The first expression must be a string. The other expressions can be of any type. The result is a string.</p>|<p>`"the current time is " + (now())`</p><p> Returns  "the current time is 2019-09-23T09:30:06.693Z"</p><p>`(now()) + " is the current time"`</p><p>Returns 2019-09-23T09:30:06.693Z is the current time</p><p>`"a" + "b" + "c" + 1234 `</p><p>Returns abc1234</p>|
|Date|+|`<expression + <duration>`<p>Append a duration to a dateTime, a dateTimeOnly or a duration.</p>|`toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")`<p>Returns 2011-12-03T15:30:30Z</p>`toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")`<p>Returns 2011-12-03T15:30:30</p>`now() + toDuration("PT1H")`<p>Returns a dateTime (with UTC timezone) one hour later from current time</p>`toDuration("PT1H") + toDuration("PT1H")`<p>Returns returns PT2H</p>|
