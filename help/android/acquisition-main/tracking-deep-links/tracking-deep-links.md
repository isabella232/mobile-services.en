---
description: You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile Android SDK.
keywords: android;library;mobile;sdk
seo-description: You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile Android SDK.
seo-title: Tracking Deep Links in Adobe Mobile Services
solution: Experience Cloud,Analytics
title: Tracking Deep Links
topic: Developer and implementation
uuid: ebb1c08c-a246-40b3-9ac6-4606a14b4c5a
---

# Tracking deep links {#tracking-deep-links}

You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile Android SDK.

## Tracking deep links

1. Add the SDK to your project and implement Lifecycle metrics.

   For more information, see *Add the SDK and Config File to your IntelliJ IDEA or Eclipse Project* in [Core Implementation and Lifecycle](/help/android/getting-started/dev-qs.md). 

1. Register the application to handle URLs.

    For more information, see [URLs](https://developer.android.com/training/basics/intents/filters.html).
1. Pass Activity with deep link intent to Adobe SDK by using `collectLifecycleData`.

   Here is a sample track deep link:

   ```java
   public class ParseDeepLinkActivity extends Activity { 
       @Override 
       protected void onCreate(Bundle savedInstanceState) { 
           super.onCreate(savedInstanceState); 

           Config.collectLifecycleData(this); 
           ... 
       } 
   }
   ```

The Adobe Mobile SDK can parse key and value pairs of data that is appended to any Deep or Universal Link as long as the link contains a key with the `a.deeplink.id` label and a corresponding non-null and user-generated value. All key and value pairs of data that are appended to the link will be parsed, attached to a lifecycle hit, and sent to Adobe Analytics as long as the link contains the `a.deeplink.id` key and value.

Additionally, you might append one or more of the following reserved keys (with user-generated values) to the deep or Universal Link:

* `a.launch.campaign.trackingcode` 
* `a.launch.campaign.source` 
* `a.launch.campaign.medium` 
* `a.launch.campaign.term` 
* `a.launch.campaign.content`

These keys are pre-mapped variables for reporting in Adobe Analytics. For more information on mapping and processing rules, see [Processing Rules and Context Data](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html).

## Tracking deferred deep links (for use with Marketing Links)

With a deferred deep link, the Adobe SDK will open a new Intent with the deep link as the intent data. This process is handled as an external deep link using the code above.

## Deep link public information {#section_1815396353614DA8A63D8D92112217E7}

### Constants

```java
/* 
 * Used for message deep link tracking
 * Key for deep link URL. 
 */
public static final String ADB_MESSAGE_DEEPLINK_KEY = "adb_deeplink";
```

