---
description: You can configure experience options for push messages and rich push messages, including name, message text, and destination options. You can also configure advanced options, including payload options and custom options for iOS devices.
keywords: mobile
seo-description: You can configure experience options for push messages and rich push messages, including name, message text, and destination options. You can also configure advanced options, including payload options and custom options for iOS devices.
seo-title: Experience  Push Message
solution: Experience Cloud,Analytics
title: Experience  Push Message
topic: Metrics
uuid: 1a8baf3e-9fea-452c-b0fc-4ba8ac270861
---

# Experience: push message {#experience-push-message}

You can configure experience options for push messages and rich push messages, including name, message text, and destination options. You can also configure advanced options, including payload options and custom options for iOS devices.

1. On the Audience page for a new push message, click **[!UICONTROL Experience]**.

   ![experience push message screen](assets/experience-push-message.png)

1. Type a name for this message.
1. Type information in the following fields in the **[!UICONTROL Message]** section:

    * **[!UICONTROL Content]**

       Specify the text of your message. You can specify up to a maximum of 140 characters.

    * **[!UICONTROL Media URL]**

      Type the URL of the media file that you plan to use in the push notification message. For requirements to use rich push notifications, see *Requirements for Rich Push Notifications* below.
  
       >[!IMPORTANT]
       >
       >To display an image or a video in a push notification, remember the following:  
       > * The `attachment-url` data is handled in the push payload.
       > * The media URL must be able to handle spikes requests.

    * **[!UICONTROL Destination]**

       Select a specific destination, such as a web, deep, or hybrid link, to send users when they click-through the message. For more information, see [Destinations](/help/using/acquisition-main/c-create-destinations.md). 

      >[!TIP]
      >
      >When you use the * **[!UICONTROL Web Link]** or **[!UICONTROL Custom Link]** destination types, the destination type is not tracked. Only **[!UICONTROL Deep Links]** are tracked.

## Requirements for rich push notifications

Here are the requirements for sending rich push notifications:

* **Supported Versions**

  Rich push notifications are supported on the following versions:
  * Android 4.1.0 or later
  * iOS 10 or later
  
     >[!IMPORTANT]
     >
     >Remember the following information:
     >* Rich push messages sent to earlier versions will still be sent but only the text is displayed.
     >* There is no watch support at this time.

* **File Formats**

  Here are the supported file formats:
  * Images: JPG and PNG 
  * Animations (iOS only): GIF
  * Videos (iOS only): MP4 

* **URL Formats**
  * HTTPS only

* **Sizing**
  * Images must be in a 2:1 format, or they will be cropped.

For more information about configuring rich push notifications, see the following content:

* [Receive Push Notifications in Android](/help/android/messaging-main/push-messaging/c-set-up-rich-push-notif-android.md)
* [Receive Rich Push Notifications in iOS](/help/ios/messaging-main/push-messaging/c-set-up-rich-push-notif-ios.md)

To configure a push message on the Experience page:

1. (**Optional**) Click the **[!UICONTROL Show Advanced Options]** link to configure additional options:

    * **[!UICONTROL Payload: Data]**

      Provide a custom push payload in JSON that will be sent to the app through a push or a local notification. The limit for Android and iOS is 4KB.

    * **[!UICONTROL Apple Options: Category]**

       Provide a category for push and local notifications. For more information, see [Managing Your App’s Notification Support](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html#//apple_ref/doc/uid/TP40008194-CH4-SW9) in the *iOS Developer Library*.

    * **[!UICONTROL Apple Options: Sound]**

       Provide the name of the sound file in your app bundle to play. A default alert sound plays if not set. For more information, see [Managing Your App's Notificaton Support](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html#//apple_ref/doc/uid/TP40008194-CH4-SW10) in the *iOS Developer Library*.

    * **[!UICONTROL Apple Options: Content Available]**

       Select this option so that when the message arrives, iOS wakes up your app in the background and allows your app to execute code based on the message payload. For more information, see [Apple Push Notification Service](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html#//apple_ref/doc/uid/TP40008194-CH8-SW1) in the *iOS Developer Library*.

1. (Optional) Preview the layout of your message by clicking following icons:

   * **[!UICONTROL x Summary]**

     Hides the preview pane. Click ![preview](assets/icon_preview.png) to display the preview pane again.

   * **[!UICONTROL Change the orientation]**

     To change the orientation of the preview from portrait to landscape mode, click ![orientation](assets/icon_orientation.png). For watches, the orientation changes from a round watch face to a square watch face.

   * **[!UICONTROL Preview on a user's watch]**

      To preview your message as it will appear on a users's watches click ![watch icon](assets/icon_watch.png).

   * **[!UICONTROL Preview on a user's mobile phone]**

      To preview your message as it will appear on a users's mobile phones click ![phone icon](assets/icon_phone.png).

   * **[!UICONTROL Preview on a user's tablet]**

     To preview your message in a user's tablet, click ![tablet icon](assets/icon_tablet.png).

   At the bottom of the preview pane, you can view a description of the audience that you selected in the previous step.

1. (**Optional**) Click **[!UICONTROL Test]** to push your message to specified devices for testing purposes.
1. Select the service and type the push tokens for at least one device to which you want to push the message.

   Specify the tokens in a comma-separated list to push the message to more than one device.

1. Configure the scheduling options for the message. 

    For more information, see [Schedule: push message](/help/using/in-app-messaging/t-create-push-message/c-schedule-push-message.md).
