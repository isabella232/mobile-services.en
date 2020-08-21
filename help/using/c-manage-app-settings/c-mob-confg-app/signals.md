---
description: Postbacks let you send data collected by Adobe Mobile to a separate third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure Mobile Services to send customized data to a third-party destination.
seo-description: Postbacks let you send data collected by Adobe Mobile to a separate third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure Mobile Services to send customized data to a third-party destination.
seo-title: Configure Postbacks
title: Configure Postbacks
uuid: a026575c-057b-4868-b6c8-9514cbc32b4d
---

# Configure postbacks {#configure-postbacks}

Postbacks let you send data collected by Adobe Mobile to a separate third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure Mobile Services to send customized data to a third-party destination.

>[!IMPORTANT]
>
>To use postbacks, you must install the 4.6 SDK or later. For more information, see [Android - Postbacks](/help/android/analytics-main/postbacks/postbacks.md) or [iOS - Postbacks](/help/ios/analytics-main/postback/postback.md).

1. Click the name of the desired app to go to its Manage App Settings page and click the **[!UICONTROL Manage Postbacks]** link at the top right side.
1. Click **[!UICONTROL Create Postback]**. 
1. Type the following information in the fields:

   * **[!UICONTROL Postback Type]**

     Choose **[!UICONTROL Custom]**. Templates will be available in the future.

   * **[!UICONTROL Name]**

     Specify a descriptive name for the postback.

   * **[!UICONTROL URL]**

     Specify a valid endpoint URL (with appropriate query parameters as needed for GET requests). You obtain this URL from the party you are sending the data to (ad server or your own endpoint). For example `https://my.server.com/?user=bob&amp;zip=90210&amp;c16=4.6.0-iOS&amp;c27=cln,132`.

   * **[!UICONTROL Context Variable]**

     Highlight portions of the URL and select the desired context variable from the drop-down list. You can also insert context variables into the URL, and the URL will replace all template variables with values from the hit.

   * **[!UICONTROL Add Post Body]**

     Specify any additional post body content, for example on a post request. If you specify post body text, specify the content type for the post body. For example, `application/json`.

   * **[!UICONTROL Timeout (in seconds)]**

     Specify the time (in seconds) to wait for the postback.

   * **[!UICONTROL Trigger(s)]**

     Specify one or more data tags and conditions that trigger the postback. For example, you might choose **[!UICONTROL Crashed]** as the trigger and **[!UICONTROL Exists]** as the condition to trigger the postback when the app crashes. You can also specify which metrics activate the postback. For example, you can select **[!UICONTROL Device Name]** as the trigger, **[!UICONTROL Equals]**, and **[!UICONTROL iPhone 6 Plus]** as conditions to activate the postback when the app crashes on iPhone 6 Plus devices.

   * **[!UICONTROL Trait(s)]**

    Specify who can see the message when it is triggered. Options include **[!UICONTROL Session Length]**, **[!UICONTROL First Launch Date]**, and **[!UICONTROL App ID]**.

1. Click **[!UICONTROL Save]** to create the postback and add it to the **[!UICONTROL Manage Postbacks]** list.

   To activate the postback in the future, do one of the following:

   * Select the checkbox next to the postback in the **[!UICONTROL Manage Postbacks]** list and click **[!UICONTROL Activate Selected]**.
   * Click **[!UICONTROL Save & Activate]** to save your changes and immediately activate the postback.
