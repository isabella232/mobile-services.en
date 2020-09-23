---
description: Here is some information to help you configure the Android extension, which allows you to collect data from your Android Wearable app.
seo-description: Here is some information to help you configure the Android extension, which allows you to collect data from your Android Wearable app.
seo-title: Android Wearables  Additional Notes
solution: Experience Cloud,Analytics
title: Android Wearables  Additional Notes
topic: Developer and implementation
uuid: 3bcf352b-4d46-4ab3-81ec-c27e86fe9be3
---

# Android Wearables: additional notes{#android-wearables-additional-notes}

Here is some information to help you configure the Android extension, which allows you to collect data from your Android Wearable app.

* The Adobe Mobile Android Wearables extension requires Android version 4.4 (KitKat) or above. 
* There is one additional context value, `A.RunMode`, which has been added to indicate whether the data comes from the containing app or the extension.

  * `RunMode` = `Application` 
  
     The hit comes from the handheld app.

  * `RunMode` = `Extension`
  
    The hit comes from the wearable app.

* The SDK automatically syncs the `aid`/`vid`/`visitor` `service id`/`privacy` status from the handheld app to the wearable app, so do not call `setPrivacyStatus`/`setUserIdentifier`/`idSync` from the wearable app. 
* [In-app messages](/help/android/messaging-main/messaging/messaging.md), [Target](/help/android/target-main/target.md), and [Audience Manager](/help/android/audience-manager/audiencemgmt.md) are disabled for the wearable app.

