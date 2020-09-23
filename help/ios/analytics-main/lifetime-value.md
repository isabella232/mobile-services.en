---
description: Lifetime value lets you measure and target on a lifetime value for each user.
seo-description: Lifetime value lets you measure and target on a lifetime value for each user.
seo-title: Visitor lifetime value
solution: Experience Cloud,Analytics
title: Visitor lifetime value
topic: Developer and implementation
uuid: d830d18b-4313-43bb-8d75-3789869d0f1d
---

# Visitor lifetime value {#visitor-lifetime-value}

Lifetime value lets you measure and target on a lifetime value for each user.

Each time you send in a value with `trackLifetimeValueIncrease`, the value is added to the existing value. Lifetime value is stored on device and can be retrieved at any time by calling `lifetimeValue`. This can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.

## Track the visitor lifetime value {#section_390943A49AF841F2941E65D6DF2B3F5A}

1. Add the library to your project and implement lifecycle.

   For more information, see *Add the SDK and Config File to your Project* in [Core Implementation and Lifecycle](/help/ios/getting-started/dev-qs.md). 
1. Import the library: 

   ```objective-c
   import com.adobe.mobile.*;
   ```

1. Call `trackLifetimeValueIncrease` with the amount to increase the value: 

   ```objective-c
   [ADBMobile trackLifetimeValueIncrease:increaseAmount data:nil];
   ```

## Send additional data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the lifetime value, you can send additional context data with each track action call:

```objective-c
NSMutableDictionary *contextData = [NSMutableDictionary dictionary]; 
[contextData setObject:imageName forKey:@"myapp.ImageLiked"]; 
[ADBMobile trackLifetimeValueIncrease:increaseAmount data:contextData];
```

Context data values must be mapped to custom variables: 

![](assets/map-variable-context-ltv.png)

