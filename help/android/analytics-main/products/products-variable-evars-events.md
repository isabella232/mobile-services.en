---
description: Here is an example of the products variable with Merchandising eVars and product-specific events.
keywords: android;library;mobile;sdk
seo-description: Here is an example of the products variable with Merchandising eVars and product-specific events.
seo-title: Products Variable with Merchandising eVars and Product-Specific Events
solution: Experience Cloud,Analytics
title: Products Variable with Merchandising eVars and Product-Specific Events
topic: Developer and implementation
uuid: 64f822a0-6ccf-48e7-8886-31b93d8198a3
---

# Products variable with merchandising eVars and product-specific events {#products-variable-with-merchandising-evars-and-product-specific-events}

Here is an example of the products variable with Merchandising eVars and product-specific events.

```java
//create a context data dictionary 
HashMap cdata = new HashMap<String, Object>(); 
  
// add products, a purchase id, a purchase context data key, and any other data you want to collect. 
// Note the special syntax for products 
cdata.put("&&events", "event1"); 
cdata.put("&&products", ";Running Shoes;1;69.95;event1=5.5;eVar1=Merchandising,;Running Socks;10;29.99"); 
cdata.put("myapp.purchase", "1"); 
cdata.put("myapp.purchaseid", "1234567890"); 
  
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
Analytics.trackAction("purchase", cdata); 
// trackState example: 
Analytics.trackState("Order Confirmation", cdata);
```

>[!TIP]
>
>If you trigger a product-specific event by using the *`&&products`* variable, you must also set that event in the *`&&events`* variable. If you do not set that event, it is filtered out during processing.

