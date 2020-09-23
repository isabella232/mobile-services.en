---
description: This information can help you troubleshoot your in-app messaging issues.
keywords: mobile
seo-description: This information can help you troubleshoot your in-app messaging issues.
seo-title: Troubleshooting In-App Messaging
solution: Experience Cloud,Analytics
title: Troubleshooting In-App Messaging
topic: Metrics
uuid: 8813e8d8-bb1e-46ad-83cd-98ae68f73ce6
---

# Troubleshooting in-app messaging{#troubleshooting-in-app-messaging}

This information can help you troubleshoot your in-app messaging issues.

 If you completed all the requirements for In-App Messaging, but messages do not show up, verify the following items: 

## Are you putting the new configuration and new SDK in the app?

* Verify that the SDK is version 4.2 or higher and is correctly configured. 

* Ensure that you have a [Messaging](/help/using/in-app-messaging/in-app-messaging.md) section in your configuration (the downloaded JSON file) or have a Messages remote endpoint, so that it can be retrieved from dynamic tag management.

## My full screen message in Android is not showing up. I am using the correct SDK, configuration, and my triggers are being met.

Did you update your manifest file to define the full screen activity?

## My local notification message in Android isn't working.

  Verify that the local notification broadcast receiver is declared in your manifest. For more information, see step #1 in [In-app messaging](/help/android/messaging-main/messaging/messaging.md).

## Is the message live?

  Check the list view in the **[!UICONTROL Status]** column on the Manage In-App Message page and verify whether the message is live. 

## Look at *show once*, *show always*, *show offline* settings on the Audience page.

  Verify that these settings are correct. On the Audience page, review the options on the **[!UICONTROL Trigger]** tab, where you can specify how often the message is displayed.

## If using launch event as trigger...

  Launch only fires on a new session. For information on when a session begins, see `lifecycleTimeout` in the [ADBMobile JSON config](/help/ios/configuration/json-config/json-config.md) file.

## I updated my message remotely but my app is still showing the old message.

Complete one of the following tasks: 

* Dynamic tag management might take a few minutes to update its endpoint with your new definition. 
  
  Give it some time and try again. 

* The config will only update on a new launch. 
  
  If the app was restarted in the life cycle session timeout, your new config might not have been downloaded.

## My image does not fit exactly into the space provided by the template.

The In-App Message full-screen template supports showing an image from a remote server (Image URL) or from the app bundle (Bundled Image). The image should be in a standard image format, for example, JPG, GIF, or PNG. 
  
Due to device screens having many different dimensions, the image probably not fit exactly into the space provided by the template. The template always focuses on showing the center of the image and crops (portrait) or fades (landscape) the sides if the image does not fit. 
  
Here is the exact placement and sizing rules for each orientation: 
  
* **Portrait**, where the image is scaled to height of 195px for phone, 529px for tablet, centered if image width is smaller than device width, and cropped if image width is greater than device width. 

* **Landscape**, where the image is scaled to 100% of height of device, width is 75% of the device, and with a fade out on the right.
  
  If you have issues with the full-screen template, you can download and use the Custom HTML template. The Custom HTML template provides greater flexibility for images and allows full control of the template.

## My messages are not reflecting changes/updates I have made in the UI.

The SDK fetches new/updated messages at the time of a lifecycle launch. This is only when the application is closed/backgrounded for greater than the lifecycle timeout value and then re-opened. 

Complete the following steps: 

  1. Curl your messages URL in your config file to verify the remote message is updated (for example, `curl "https://assets.adobedtm.com/b213090c5204bf94318f4ef0539a38b487d10368/scripts/satellite-542c62859662383b1a0008f4.json"`) 
  1. Close the application.  
  1. Wait for a time period that is longer than the `lifecycleTimeout` in the config file. 
  1. Open the app, navigate to where the message should be displayed, and verify that it has been updated.