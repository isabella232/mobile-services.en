---
description: You can configure your app to use Apple Push Notification Service (APNS) or Firebase Cloud Messaging (FCM).
keywords: mobile
seo-description: You can configure your app to use Apple Push Notification Service (APNS) or Firebase Cloud Messaging (FCM).
seo-title: Configure App to use APNS or FCM
solution: Experience Cloud,Analytics
title: Configure App to use APNS or FCM
topic: Metrics
uuid: fa411f2a-ba47-4499-bbe5-1aedef6b49ad
---

# Configure your app to use APNS or FCM{#configure-app-to-use-apns-or-fcm}

You can configure your app to use Apple Push Notification Service (APNS) or Firebase Cloud Messaging (FCM).

## Android Apps {#section_41D304102CDF4586911EC1413AD35A10}

### If FCM is not enabled in your app

To configure your Android app to use FCM in this scenario:

1. Go to [https://firebase.google.com/](https://firebase.google.com/) and log in with your Google Dev credentials.

1. Click **[!UICONTROL Get Started]** and select **[!UICONTROL Add Project]**.

1. Enter a project name and if opting in to Google Analytics for Firebase data, click the checkbox accepting the controller-controller terms.

1. Click **[!UICONTROL Create project]** and wait for the project to be created.

1. Click on the created project and the **[!UICONTROL Project Overview]** page for the created project should be shown. Click the button with the Android icon to add an Android app to the project.

1. Enter the app package name, app nickname, and signing certificate if needed.

1. Follow the additional steps suggested by the setup wizard. After verifying the Firebase setup by testing communication with the Firebase servers, return to the **[!UICONTROL Project Overview]** page.

1. Click the gear icon to the right of the **[!UICONTROL Project Overview]** button and click **[!UICONTROL Project Settings]**.

1. Click the **[!UICONTROL Cloud Messaging]** tab. 

1. Copy the **[!UICONTROL Legacy server key]** and **[!UICONTROL Sender ID]** for later use.

   For example:

   ```
   - Legacy server key = AIzaSyC6FNgsCOpBL5eXhDvwf8979mWba6x7Roo
   ```

   ```
   - Sender ID = 835015092250
   ```

### If FCM is enabled in your app

To configure your Android app to use FCM in this scenario:

1. Go to [https://firebase.google.com/](https://firebase.google.com/) and log in with your Google Dev credentials.

1. Click **[!UICONTROL Get Started]**. This will open the project index page. Find the Firebase enabled project which is linked to your Android app and click the project card.

1. The **[!UICONTROL Project Overview]** for the project should then be loaded. Click the gear icon to the right of the **[!UICONTROL Project Overview]** button and click **[!UICONTROL Project Settings]**.

1. Click the **[!UICONTROL Cloud Messaging]** tab. 

1. Copy the **[!UICONTROL Legacy server key]** and **[!UICONTROL Sender ID]** for later use.

   For example:

   ```
   - Legacy server key = AIzaSyC6FNgsCOpBL5eXhDvwf8979mWba6x7Roo
   ```

   ```
   - Sender ID = 835015092250
   ```



## iOS apps {#section_2031DAB485FC4D2B9027E42AD90B294D}

To configure your iOS app to use APNS:

1. Go to [https://developer.apple.com/account](https://developer.apple.com/account) and log in to your [Apple Developer account](https://developer.apple.com/account). 
1. Under **[!UICONTROL iOS Apps]**, select **[!UICONTROL Identifiers]**. 
1. If you have an App ID set up for push, go to Step 11. 
1. Press the **[!UICONTROL +]** button to create a new App ID. 
1. Type an App ID Description. 
1. Type an App ID Suffix.

   >[!IMPORTANT]
   >
   >To support push, you must use an Explicit App ID that does **not** use a wild card (for example, `- com.tester.pushSample`).

1. Under **[!UICONTROL App Services]**, select the **[!UICONTROL Push Notifications]** check box. 
1. Click **[!UICONTROL Continue]**. 
1. Click **[!UICONTROL Submit]**. 
1. Click **[!UICONTROL Done]**. 
1. Select your App ID that is set up to use push messaging from the list and click **[!UICONTROL Edit]**. 
1. If you already have a Push Certificate created, skip to Step 15. 
1. Scroll down to **[!UICONTROL Push Notifications]** and click the correct **[!UICONTROL Create Certificate...]** button.

   The button you click depends whether you are creating a certificate for Development or Production. 
1. Follow the steps on how to create your CSR on Apple's website, upload the CSR, and generate your certificate. 
1. Scroll down to the **[!UICONTROL Push Notifications]** section and download the SSL certificate you just created. 
1. Double-click the downloaded certificate to add it to your keychain.

### SSL certificate and private keys

To get your SSL certificate and private key (APNS):

1. Open **[!UICONTROL Keychain Access]**. 
1. Click **[!UICONTROL My Certificates]** and find the appropriate **[!UICONTROL iOS Push Services Certificate]** for your app and environment.

   You can identify the correct certificate by matching the bundle ID and whether it is Development or Production. 

1. Expand the certificate and verify that it contains a private key. 
1. Right-click the private key and select **[!UICONTROL  Export " *`<name of key>`*]**. 
1. Type the necessary information in the dialog box and save your new `.p12` file.

   You do not have to type a password. 

1. In the **[!UICONTROL Private Key]**, type the `.p12` file.

