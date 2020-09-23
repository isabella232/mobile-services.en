---
description: Frequently asked questions and answers for Adobe Mobile Services and a general description of features.
keywords: mobile
seo-description: Frequently asked questions and answers for Adobe Mobile Services and a general description of features.
seo-title: Frequently Asked Questions
solution: Experience Cloud,Analytics
title: Frequently Asked Questions
topic: Metrics
uuid: 62a9241c-2ada-483a-a594-b023916cb0b6
---

# Frequently Asked Questions {#frequently-asked-questions}

The following table contains a list of frequently asked questions for Adobe Mobile Services:

## Adobe Mobile SDK {#section_9C2181F7B39A4BEB8EE6BCEFCF14C72F}

### Do you make frequent updates with the SDK? 

Yes, we are constantly making updates in effort to get you the most feature rich, standard-compliant, and secure SDKs. We typically release a new version every month. These SDK updates are drop-in replacements (for version 4x) to aid in ease of implementation. For more information on our updates, see our [Release Notes](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html). 

### What SDK version should I be on? 

Our current SDKs are on version 4.11. For more information, see our [Release Notes](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html). 

### Where can I download the SDKs? 

The SDKs for individual mobile platforms may be downloaded by visiting the [Manage App Settings](/help/using/c-manage-app-settings/c-manage-app-settings.md) section. 

### How do I configure the SDKs? 

After you create a new app report suite, navigate to Manage App Settings and configure all of the required options on the app information page. After you save your configuration, download the required SDKs from the bottom of the Manage App Settings page. The SDK will come pre-configured with the options you have saved and can be found in the `ADBMobileConfig.json` file in the SDK package. If you change any SDK settings on the Manage App Settings page, make sure you re-download the SDK files or update your `ADBMobileConfig.json` file with the necessary changes. 

### Do the Adobe Mobile SDKs support IPv6 for iOS? 

The Adobe Mobile SDKs use the standard iOS and Android network stacks. For iOS, the SDK uses NSURLSession (iOS versions 7+) and NSURLConnection (iOS versions 7 and later) which are fully compliant with IPv6. Developers who have built or use their own networking stack might want to review if there are other mitigating considerations. Here is some additional information from Apple: 

*If you're writing a client-side app using high-level networking APIs such as NSURLSession and the CFNetwork frameworks and you connect by name, you should not need to change anything for your app to work with IPv6 addresses.* For more information see, [Supporting IPv6 DNS64/NAT64 Networks](https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#__/apple_ref/doc/uid/TP40010220-CH213-SW1).


## Adobe Analytics {#section_78EC9D83791F477AAED678720CEBA9F6}

### What are Lifecycle Metrics?

Lifecycle Metrics are "out-of-the-box" metrics that are automatically collected when the SDK is first implemented in your app. For more information, see [Lifecycle Metrics (Android)](/help/android/metrics.md) and [Lifecycle Metrics (iOS)](/help/ios/metrics.md).

### How can I troubleshoot processing rules? 

For more information, see [Processing Rules Tips and Tricks](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-tips.html). 

### Can I send my analytics data to multiple report suites?

Yes. The SDKs provide the ability to send data to multiple Adobe Analytics report suites. To capture data in multiple report suites by using an image request, set the multiple report suite IDs in the **[!UICONTROL rsids]** field under **[!UICONTROL analytics]** section in the `ADBMobileConfig.json` file, delimited by commas and no spaces. For more information, see [ADBMobile JSON Config](/help/ios/configuration/json-config/json-config.md). 

### How are Mobile visits different from launches? 

A launch is measured by the SDK when a user opens the app for the first time or returns to the app after having been out of the app for longer than the specified timeout value. The typical timeout is 5 minutes (300 seconds) in **[!UICONTROL lifecycleTimeout]** field, which is located in the `ADBMobileConfig.json` file. A visit is a server-side calculation by Adobe Analytics and is based on the first and last data hits that are sent by the SDK without exceeding a visit timeout. Typically, session timeouts are set at 30 minutes for a report suite. Although visits come from traditional web analytics, these hits still provide valuable insights into how users enter and exit from your app. 

## Messaging {#section_5EFDD2B2EBA543C09902FF979C89F2EC}

### Are there size or other limitations on push notifications?

Push notification messages have a 140 character limit. There are no limits on how many notifications might be sent or scheduled or how often notifications are sent. 

### Do you support custom payloads for push notifications? 

Yes, we provide for a custom push payload that may coded in JSON. Android and iOS payloads are restricted to 4KB and 2KB respectively. These payloads are sent to the app via a push or a local notification. For more information, see [Experience: Push Message](/help/using/in-app-messaging/t-create-push-message/c-experience-push-message.md). 

### Are there size limitations on in-app messages? 

Published and active in-app messages created in Adobe Mobile Services are hosted on a server with a 15MB size restriction per app report suite. While this restriction applies to message content and resources hosted with Adobe, there are no restrictions on what resources the in-app message may refer to on other hosts or those within the app.

### Can I use my own HTML for in-app messages? 

Yes, we support custom HTML for your in-app messages. For more information, see [Experience: In-App Message](/help/using/in-app-messaging/t-in-app-message/c-experience-in-app-message.md).

### What triggers can I use to send push notifications or in-app messages?

Marketers may choose any Analytics data or event that is being sent as a trigger to display in-app messages. In-app messages use triggers that happen locally on the device. If multiple triggers are chosen, all triggers must occur in the same hit for the message to display. For more information, see [Experience: In-App Message](/help/using/in-app-messaging/t-in-app-message/c-experience-in-app-message.md).

Push messages are sent using pre-existing Adobe Analytics segments or custom segments that may be created on historic Analytics data already collected. For more information, see [Experience: Push Message](/help/using/in-app-messaging/t-create-push-message/c-experience-push-message.md). 

### Why am I getting an error with the in-app, push, or Marketing Link name that I typed? 

You cannot use the same in-app message, push message, or marking link name in multiple apps that use the same parent report suite or VRS. To resolve this issue, enter another name for your in-app message, push message, or Marketing Link. 

## Location {#section_01208FE3B7764E0DADDCB9AD9E1FCD87}

### Is there a limit on how many oints of interest (POIs) I can have? 

There no specific restriction, but for ideal performance and due to memory restrictions on the user's device, we recommend that you create or upload a maximum of 5000 POIs.

## Acquisition {#section_B37F1129CD5843E890D0E54179455357}

### Can I attribute campaigns to in-app activities? 

Yes. Adobe Mobile Services can help you build marketing tricks that help promote and drive traffic to your apps and tie acquisition campaigns to in-app analytics and conversions. For more information, see [Acquisition](/help/using/acquisition-main/acquisition-main.md). 

### How can I set up links to acquire and track new app users? 

You can create Marketing Links that route users to download applications from the Apple App Store and Google Play. These links allow you to attribute your success events to the downloads. For more information, see [Marketing Links Builder](/help/using/acquisition-main/c-marketing-links-builder/c-marketing-links-builder.md).