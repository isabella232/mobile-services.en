---
description: This information helps you with a GDPR data deletion request.
seo-description: This information helps you with a GDPR data deletion request.
seo-title: Setting the User's Opt Status
solution: Experience Cloud,Analytics
title: Setting the User's Opt Status
topic: Developer and implementation
uuid: 44a09a25-93c6-4e1a-b69e-710018e8b6c3
---

# Setting the user's opt status {#setting-the-user-s-opt-status}

This information helps you with a GDPR data deletion request.

>[!IMPORTANT]
>
>Starting with Experience Cloud iOS SDKs 4.15, setting the privacy status to `unknown` holds Audience Manager and Experience Cloud ID hits.

You can control whether Analytics, Target, and Audience Manager activity is allowed on a device by using the following settings:

* `privacyDefault` in [ADBMobile JSON Config](/help/ios/configuration/json-config/json-config.md).

  This setting controls the initial setting that persists until it is changed in code. 

* `setPrivacyStatus` method.

  After the privacy setting is changed by using this method, the change is permanent until it is changed again by using this method, or when you uninstall and install the app again.

  For more information about the methods, see [Configuration Methods](/help/ios/configuration/json-config/json-config.md).

Here is information about each privacy status:

* **Opt in**

  * Analytics: Hits are sent. 
  * Target: Mbox requests are sent.  
  * Audience Manager: Signals and ID syncs are sent.
  * Value in the JSON config file: `optedin`
  * Value in `setPrivacyStatus`: `ADBMobilePrivacyStatusOptIn`

* **Opt out**

  * Analytics: Hits are discarded. 
  * Target: Mbox requests are not allowed.  
  * Audience Manager: Signals and ID syncs are not allowed.
  * Value in the JSON config file: `optedout`
  * Value in `setPrivacyStatus`: `ADBMobilePrivacyStatusOptOut`

* **Unknown**

  * Analytics: If offline tracking **is** enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). 
  
    If offline tracking **is not** enabled, hits are discarded until the privacy status changes to opt-in.  

  * Target: Mbox requests are sent.
  * Audience Manager: Signals and ID syncs are sent.
  * Value in the JSON config file: `optunknown`
  * Value in `setPrivacyStatus`: `ADBMobilePrivacyStatusUnknown`

## Examples {#section_128AC455EE024193B5D4E5A565B53D00}

```objective-c
- (IBAction) setPrivacyOptIn { 
 [ADBMobile setPrivacyStatus:ADBMobilePrivacyStatusOptIn]; 
} 
- (IBAction) setPrivacyOptOut { 
 [ADBMobile setPrivacyStatus:ADBMobilePrivacyStatusOptOut]; 
} 
- (IBAction) setPrivacyOptUnknown { 
 [ADBMobile setPrivacyStatus:ADBMobilePrivacyStatusUnknown]; 
}
```

