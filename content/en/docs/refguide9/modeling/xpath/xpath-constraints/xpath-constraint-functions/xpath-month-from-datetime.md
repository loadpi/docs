---
title: "XPath month-from-dateTime"
url: /refguide9/xpath-month-from-datetime/
tags: ["studio pro"]
---

## 1 Overview

The `month-from-dateTime()` function extracts the month value from a **Date and time** attribute so it can be used to compare to a value.

## 2 Syntax

The syntax is as follows:

```
month-from-dateTime ( attribute [, timezone ] )
```

### 2.1 attribute

`attribute` specifies the attribute to extract the day from. Attribute must be of the **Date and time** type.

### 2.2 timezone

{{% alert color="info" %}}
The optional `timezone` parameter is available in [Studio Pro 9.22.0](/releasenotes/studio-pro/9.22/) and above. 
{{% /alert %}}

`timezone` specifies the time zone to use for the extraction. This parameter is optional and defaults to the local time zone. It should be a string literal containing an IANA time zone or `'UTC'`. GMT offset time zones are not supported.

## 3 Examples

This query returns all logs where the month value `DateAttribute` is 12 (December) in the local time zone (for example, "2011-12-30"):

```java {linenos=false}
//Logging.Log[month-from-dateTime(DateAttribute) = 12]
```

This query returns all logs where the month value `DateAttribute` is 12 (December) in the New York time zone (for example, "2011-12-30"):

```java {linenos=false}
//Logging.Log[month-from-dateTime(DateAttribute, 'America/New_York') = 12]
```
