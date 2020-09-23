---
description: Configure experience options for in-app messages, including type (full screen, alert, or notification) and display, text, and button options.
keywords: mobile
seo-description: Configure experience options for in-app messages, including type (full screen, alert, or notification) and display, text, and button options.
seo-title: Experience  In-App Message
solution: Experience Cloud,Analytics
title: Experience  In-App Message
topic: Metrics
uuid: 4c6d6756-47fb-4f1b-8338-0b0c9b0fceb0
---

# Experience: in-app message {#experience-in-app-message}

Configure experience options for in-app messages, including type (full screen, alert, or notification) and display, text, and button options.

1. In your app, click **[!UICONTROL Messaging]** > **[!UICONTROL Manage Messages]** > **[!UICONTROL Create Message]** > **[!UICONTROL Create In-App]**.
1. On the Experience page, type a name for the message.
1. Complete the fields in the **[!UICONTROL Type]** section:

   * **[!UICONTROL Type]**
     Select the message type for your in-app message campaign:  

     * **[!UICONTROL Full Screen]**
     * **[!UICONTROL Alert]**
     * **[!UICONTROL Local Notification]**

   * **[!UICONTROL Template]**

     Customize a themed responsive message template for your content.
  
     >[!TIP]
     >
     >This option is displayed only when you select the **[!UICONTROL Full Screen]** message type.
  
   * **[!UICONTROL Custom]**
  
     Load your custom HTML content (full screen only). You must provide a click-through link and a cancel link.
  
     1. Click **[!UICONTROL Browse]** and download an HTML file or drag an HTML document to the window.
     1. Click **[!UICONTROL Download Example]** to view sample custom HTML content.
  
     >[!TIP]
     >
     >This option is displayed only when you select the **[!Full Screen]** message type.

1. Complete the fields in the **[!UICONTROL Display]** section:

   * **[!UICONTROL Theme]**

    Select a theme for your message.

   * **[!UICONTROL Layout]**

      Select the app layout on the device screen.

   * **[!UICONTROL Image URL]**

      The URL for an image. If you have sizing issues when using the full-screen template, see *My image does not fit exactly into the space provided by the template* in [Troubleshooting in-app messaging](/help/using/in-app-messaging/t-in-app-message/in-apps-ts.md).

   * **[!UICONTROL Bundled Image]**

      Path to an image in your app code bundle. This option is used when there is no image. or the image is unavailable. The imagine might not be available if, for example, the device is offline. If you have sizing issues when using the full-screen template, see *My image does not fit exactly into the space provided by the template* in [Troubleshooting in-app messaging](/help/using/in-app-messaging/t-in-app-message/in-apps-ts.md).

1. Complete the fields in the **[!UICONTROL Text]** section:

   * **[!UICONTROL Header]**

     Type the text for the message's header.

   * **[!UICONTROL Content]**

     Type the text for the message's content.

1. Complete the fields in the **[!UICONTROL Buttons]** section:

   * **[!UICONTROL Click-Through Button]**

      Label for the **[!UICONTROL Click-Through]** button. Tapping this button counts as a successful click-through. The user is redirected to the destination.

   * **[!UICONTROL Destination]**

     Select a specific destination, such as a web, deep, or hybrid link, to send users when they click-through the message. The redirect URL for a successful click-through. 
  
     This URL might contain the following information:

     * `{userId}`, which is replaced with the user identifier or is blank when the user identifier is not set.  
     * `{trackingId}`, which is replaced with the aid (correlates with *s_vi* cookie).
     * `{messageId}`, which is replaced with the unique ID for the in-app message.
     * `{lifetimeValue}`, which is replaced with the lifetime value or 0 if no lifetime value exists.

     Here is an example of tracking the user ID: `https://www.mysite.com?uid={userId}`.

     If the click-through URL uses `https://` or `https://`, the URL opens in the device browser outside the app. Otherwise, each platform supports schemes that allow you to open or reference your app if the app has been developed to support the custom scheme. 

     >[!TIP]
     >
     >When you use the **[!UICONTROL Web Link]** or **[!UICONTROL Custom Link]** destination types, the destination type is not tracked. Only **[!UICONTROL Deep Links]** are tracked. For more information, see [Destinations](/help/using/acquisition-main/c-create-destinations.md).

1. (Optional) Preview the layout of your message by clicking following icons:

   * **[!UICONTROL Summary]** hides the preview pane. 
  
     Click ![preview](assets/icon_preview.png) to redisplay the preview pane.

   * **[!UICONTROL Change the orientation]**
  
     To change the orientation of the preview from portrait to landscape mode, click ![orientation](assets/icon_orientation.png). For watches, the orientation changes from a round to a square watch face.

   * **[!UICONTROL Preview on a user's watch]**

     To preview your message as it will appear on a user's watch, click ![watch icon](assets/icon_watch.png).

   * **[!UICONTROL Preview on a user's mobile phone]**

     To preview your message as it will appear on a users's mobile phone click ![phone icon](assets/icon_phone.png).

   * **[!UICONTROL Preview on a user's tablet]**

     To preview your message in a user's tablet, click ![tablet icon](assets/icon_tablet.png).

     At the bottom of the preview pane, you can view a description of the audience that you selected in the previous step. You can also view a description of the audience you selected in the previous step at the bottom of the preview pane.

1. Configure [Schedule options](/help/using/in-app-messaging/t-in-app-message/c-schedule-in-app-message.md).
