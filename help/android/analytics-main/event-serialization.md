---
description: Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.
keywords: android;library;mobile;sdk
seo-description: Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.
seo-title: Event Serialization
solution: Experience Cloud,Analytics
title: Event Serialization
topic: Developer and implementation
uuid: acdeda16-ab83-4cfc-907d-33448b801b31
---

# Event serialization {#event-serialization}

Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.

```java
cdata.put("&&events", "event1:12341234");
```

For example:

```java
//create a context data dictionary 
HashMap cdata = new HashMap<String, Object>(); 
 
// add events 
cdata.put("&&events", "event1:12341234"); 
 
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
Analytics.trackAction("action", cdata); 
// trackState example: 
Analytics.trackState("State Name", cdata);
```

