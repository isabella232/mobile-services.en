---
description: You can define and configure audience options for push messages, including date range options, Analytics segments, and custom segments.
keywords: mobile
seo-description: You can define and configure audience options for push messages, including date range options, Analytics segments, and custom segments.
seo-title: Audience  Define and Configure Audience Segments for Push Messages
solution: Marketing Cloud,Analytics
title: Audience  Define and Configure Audience Segments for Push Messages
topic: Metrics
uuid: efd410e7-3b6c-4cf4-a26f-b11688adc491
---

# Audience: push messages{#audience-define-and-configure-audience-segments-for-push-messages}

You can define and configure audience options for push messages, including date range options, Analytics segments, and custom segments.

## Define audience segments {#section_7C4D2393CF7441959FE2381A02867CAC}

When an audience segment for push messaging is created, the segment might involve users from one or more apps because report suites or virtual report suites might contain data from one or more apps. For more information about virtual report suites, see [Virtual report suites](/help/using/manage-apps/c-mob-vrs.md).

In Adobe Mobile Services, marketers might only push to one app per platform. If marketers attempt to push to segments that contain users from multiple apps, a warning is displayed that states that proceeding can result in serious push failures and the potential deny listing of users. If you experience a push failure, see *Resolving push failures* in [Troubleshooting push messaging](/help/using/in-app-messaging/t-create-push-message/c-schedule-push-message.md).

To use Audience Manager data in your segment definition, see [Audience Analytics](https://docs-author-stg.corp.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html). 

>[!IMPORTANT]
>
>If app users are deny listed, marketers can **never** send push messages to those affected users again.

If you select an audience segment that contains users across multiple apps, you might see the following alert:

![multiple app name](assets/multiple_appname.png)

The app name is based on the pared down version of the appId, which is automatically sent to Adobe Analytics by the Mobile Services SDK in the `<app name> <version number> (<bundle id>)` format.

>[!TIP]
>
>The version number is optional.

Up to 6 sets of numbers for the version and 5 sets of numbers for the bundle ID are removed.

For example:

* `Bea[rd]cons 1.0 (123)` will appear as `Bea[rd]cons`
* `Bea[rd]cons 1.2 (1.2)` will appear as `Bea[rd]cons`
* `Bea[rd]cons 1.2.3.4.5.6.7 (1111)` will appear as `Bea[rd]cons .7`
* `Bea[rd]cons 1.2.3. (1.2.3.4.5.6)` will appear as `Bea[rd]cons (.6)`

To continue to send the push message to the listed apps, select the **[!UICONTROL Yes, I want to proceed.]** check box and click **[!UICONTROL Send]**.

## Best practices

Here are some best practices to remember:

* To reduce confusion, **avoid** defining mobile app virtual report suites that contain data from multiple apps. 
* Use a unique app ID as part of an audience segment **each** time you want to send a push message.
  This ensures that push notifications are sent to an audience segment that belongs to **only** one app.

### Examples

Here are some examples to help you understand how to correctly define segments:

**Do**: The Marketer provides push certificates for the iOS and Android versions of one app, for example, for Adobe Photoshop. The Marketer might send a push notification to a user segment that spans across both platforms.

**Do not**: Marketers provide push certificates for iOS and Android versions of one app, for example, for Adobe Photoshop. If the marketer creates and pushes to a segment of *all active users in the last 30 days*, only the users of the Adobe Photoshop iOS and Android app receive the push, and all of the Adobe Illustrator iOS and Android app users will be deny listed. For more detailed, example see *Resolving push message failures* in [Troubleshooting Push Messaging](/help/using/in-app-messaging/t-create-push-message/c-troubleshooting-push-messaging.md).

## Configure audience segments {#section_A92C60885A30421B8150820EC1CCBF13}

1. Go to the Audience page for a new push message.

    For more information, see [Create a push message](/help/using/in-app-messaging/t-create-push-message/t-create-push-message.md).

     As you configure the audience options, remember the following **important** information:

      * The **[!UICONTROL Estimated Opt-In Audience]** is the number of devices that match the Adobe Analytics segment **and** the number of opted-in devices.

        You can view an estimate of the number of users in your selected segment(s) that have opted in to receive messages and will receive the push message. The total number of app users displays below the estimate, regardless of opt-in status.

      * The **[!UICONTROL Total]** is the number of devices that match the Adobe Analytics segment.

      * Push messages are sent to the devices that are part of a defined Adobe Analytics segment **and** that have opted-in for push messages.

        This means that the SDK has sent a value of `True` for the Push Message Opt-In evar.

      * Even though the device has a valid device token, unless Adobe Analytics has set the opted-in flag, the message is not pushed to the device.

      * For more information about troubleshooting push messaging, see the following:

        * [Push messaging in iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/push-messaging.html)

        * [Push messaging in Android](https://docs.adobe.com/content/help/en/mobile-services/android/messaging-android/push-messaging/push-messaging.html)

1. Type information in the following fields:

   * **[!UICONTROL During The]**

      Type the time frame to use for the estimated audience. From the **[!UICONTROL During The]** drop-down list, select an option:

   * **[!UICONTROL Last]** lets you select a relative time frame (for example, the last 7 days, last 30 days, or last 60 days) from the time the message is scheduled to push. 

     As an example, if you select the last 30 days and schedule the message to push on October 31, the estimated audience would be the number of users who have opted-in to receive push messages the 30 days before October 31.  
  
   * **[!UICONTROL Static Range]** lets you select a static range by picking the beginning and end dates for the estimated audience range. 

     Using the previous example, if you select a date range beginning October 1 and ending October 15 but schedule the message to push on October 31, the estimated audience would be the number of users who have opted-in to receive push messages in the static date range that you specified (October 1 to October 15).

   * **[!UICONTROL Analytics Segments]**

      Select an existing Adobe Analytics segment from the drop-down list. For more information, see [Build segments](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).

   * **[!UICONTROL Custom Segments]**

      Select a metric or variable from the drop-down list (for example, **[!UICONTROL Days Since Last Use]** or **[!UICONTROL Point of Interest]**) and configure the filter as desired. For example, the following custom segment targets users who have a mobile phone running iOS and are in the California (United States) region.

   >[!IMPORTANT]
   >
   >In the **[!UICONTROL Create Audience]** section, if you click **[!UICONTROL And]**, a dialog box appears that reminds you to ensure that each app that is listed **must** have a valid certificate. If you clicked **[!UICONTROL Or]**, the default dialog box appears. For more information about valid certificates and report suites, see [Virtual report suites](/help/using/manage-apps/c-mob-vrs.md).
