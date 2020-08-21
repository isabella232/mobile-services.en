---
description: The lifetime value allows you to measure and target on a lifetime value for each Android user. The value can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.
seo-description: The lifetime value allows you to measure and target on a lifetime value for each Android user. The value can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.
seo-title: Visitor Lifetime Value
solution: Marketing Cloud,Analytics
title: Visitor Lifetime Value
topic: Developer and implementation
uuid: ba0308de-282e-46f9-a14c-19fb6d5c363e
---

# Visitor lifetime value {#visitor-lifetime-value}

The lifetime value allows you to measure and target on a lifetime value for each Android user. The value can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.

Each time you send in a value with `trackLifetimeValueIncrease`, the value is added to the existing value. Lifetime value is stored on device and can be retrieved at any time by calling `lifetimeValue`.

## Track the visitor lifetime value {#section_390943A49AF841F2941E65D6DF2B3F5A}

1. Add the library to your project and implement lifecycle.

   For more information, see *Add the SDK and Config File to your IntelliJ IDEA or Eclipse Project* in [Core implementation and lifecycle](/help/android/getting-started/dev-qs.md). 
1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. Call `trackLifetimeValueIncrease` with the amount to increase the value: 

   ```java
   Analytics.trackLifetimeValueIncrease(BigDecimal.valueOf(5.0), null);
   ```

## Send additional data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the lifetime value, you can also send additional context data with each track action call:

```java
HashMap cdata = new HashMap<String, Object>(); 
cdata.put("myapp.ImageLiked", imageName); 
Analytics.trackLifetimeValueIncrease(BigDecimal.valueOf(5.0), cdata);
```

Context data values must be mapped to custom variables in Adobe Mobile services:

![](assets/map-variable-context-ltv.png)

