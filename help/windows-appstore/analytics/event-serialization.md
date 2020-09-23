---
description: Event serialization is not supported by processing rules. In the mobile SDK, you must use a special syntax within the context data parameter to set serialized events directly on the server call.
seo-description: Event serialization is not supported by processing rules. In the mobile SDK, you must use a special syntax within the context data parameter to set serialized events directly on the server call.
seo-title: Event serialization
solution: Experience Cloud,Analytics
title: Event serialization
topic: Developer and implementation
uuid: a5966d05-e218-446f-9f19-8664a84b74cd
---

# Event serialization{#event-serialization}

Event serialization is not supported by processing rules. In the mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.

```js
cdata["&&events"] = "event1:12341234";
```

For example:

```js
//create a context data dictionary 
var cdata = new Windows.Foundation.Collections.PropertySet(); 
 
// add events 
cdata["&&events"] = "event1:12341234"; 
 
var ADB = ADBMobile; 
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
ADB.Analytics.trackAction("action", cdata); 
// trackState example: 
ADB.Analytics.trackState("State Name", cdata);
```

