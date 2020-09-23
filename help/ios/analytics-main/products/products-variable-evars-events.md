---
description: Here is an example of the products variable with Merchandising eVars and product-specific events.
seo-description: Here is an example of the products variable with Merchandising eVars and product-specific events.
seo-title: Products Variable with Merchandising eVars and Product-Specific Events
solution: Experience Cloud,Analytics
title: Products Variable with Merchandising eVars and Product-Specific Events
topic: Developer and implementation
uuid: f913211e-97ad-4237-bfe4-7ded01295caf
---

# Products variable with merchandising eVars and product-specific events {#products-variable-with-merchandising-evars-and-product-specific-events}

Here is an example of the products variable with Merchandising eVars and product-specific events.

```
//create a context data dictionary 
NSMutableDictionary *contextData = [NSMutableDictionary dictionary]; 
  
// add products, a purchase id, a purchase context data key, and any other data you want to collect. 
// Note the special syntax for products 
[contextData setObject:@"event1" forKey:@"&&events"]; 
[contextData setObject:@";Running Shoes;1;69.95;event1=5.5;eVar1=Merchandising,;Running Socks;10;29.99" forKey:@"&&products"]; 
[contextData setObject:@"1234567890" forKey:@"m.purchaseid"]; 
[contextData setObject:@"1" forKey:@"m.purchase"]; 
  
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
[ADBMobile trackAction:@"purchase" data:contextData]; 
// trackState example: 
[ADBMobile trackState:@"Order Confirmation" data:contextData];
```

>[!TIP]
>
>If you trigger a product-specific event by using the *`&&products`* variable, you must also set that event in the *`&&events`* variable. If you do not set that event, it is filtered out during processing.

