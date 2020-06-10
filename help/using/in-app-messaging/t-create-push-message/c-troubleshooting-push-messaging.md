---
description: This information can help you troubleshoot push messaging.
keywords: mobile
seo-description: This information can help you troubleshoot push messaging.
seo-title: Troubleshooting Push Messaging
solution: Marketing Cloud,Analytics
title: Troubleshooting Push Messaging
topic: Metrics
uuid: c7be4ab7-0cfe-4296-84a8-01412f4fd93f
---

# Troubleshooting push messaging{#troubleshooting-push-messaging}

This information can help you troubleshoot push messaging.

## Why are there sometimes delays sending push messages?

The following types of delays might be associated with push messages for Mobile Services:

* **Waiting for Analytics hits**
  
  Every report suite has a setting to determine when to process incoming Analytics hits. The default is every 1 hour. 
  
    The actual processing of Analytics hits might take up to 30 minutes, but is typically 15-20 minutes. For example, a report suite processes hits every hour. When you factor the required processing time of 30 minutes max, it can take up to 90 minutes for an incoming hit to be available for a push message. If a user launched the app at 9:01 AM, the hit would appear in the Mobile Services UI as a new unique user between 10:15 to 10:30 AM.  

* **Waiting for the Push Service** 
  
  The Push Service (APNS or GCM) might not immediately send out the message. Although uncommon, there have been occurrences of wait times up to 5-10 minute. You can verify that the push message has been sent to the Push Service by looking in the **[!UICONTROL Report]** view of the Push Message, finding the message in the **[!UICONTROL Message History]** table, and looking at the **[!UICONTROL Published]** count. 
  
  >[!TIP]
  >
  >This count is the number of successful sends to the Push Service(s). The Push Services do not guarantee that a message will be sent. 

  For more information about the reliability of service, see:

  * [Quality of Service](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html#//apple_ref/doc/uid/TP40008194-CH8-SW5l) 
  * [Lifetime of a Message](https://developers.google.com/cloud-messaging/concept-options#lifetime).

## Why is my Android GCM API key invalid?

* **Invalid API key**
  
  Your API key might be invalid for the following reasons: 
  
  * The API key that you provided is not a server key with the correct GCM API key value.
  * The server key has allowed the IPs and is blocking Adobe's servers from sending a push message. 
  
* **Determine the validity of the API key**
  
    To determine the validity of your API key, run the following command: 

    **Android** 

    ```java
    # api_key=YOUR_API_KEY
    #curl--header"Authorization:key=$api_key"\
        --headerContent-Type:"application/json"\ 
        https://gcm-http.googleapis.com/gcm/send\
        -d"{\"registration_ids\":[\"ABC\"]}"
    ```

    A returned 401 HTTP status code means that your API key is invalid. Otherwise, you will see something similar to this: 

    ```java
    {"multicast_id":6782339717028231855,"success":0,"failure":1,
    canonical_ids":0,"results":[{"error":"InvalidRegistration"}]}
    ```

  You can also check the validity of a registration token by replacing `"ABC"` with the token.

## Why is my APNS cert not working?

Your APNS certificate might be invalid for the following reasons:
  
* You might be using a sandbox certificate instead of the production certificate.  
* You are using a new production/sandbox certificate that is not supported.  
* You are using `.p8` file instead of a `.p12` file.

## Resolving push message failures

**An example**
  
The following example illustrates how you can resolve a push failure when using a VRS. 
  
The following customer has two iOS apps:

* App Name: PhotoShop_app_iOS
  * Parent RSID: AllAdobe PhotoShop_apps
  * VRSID: PhotoShop_iOS_app_SF
  * VRSID Definition Segment: `a.appid contains “PhotoShop_iOS_app_SF”`
* App Name: PhotoShop_app_iOS 
  * Parent RSID: AllAdobe PhotoShop_apps  
  * RSID: PhotoShop_iOS_app_LA 
  * VRSID Definition Segment: `a.os contains “iOS”`

In this example, if a Photoshop employee sends a push to the *PhotoShop_iOS_app_SF* app, all *PhotoShop_iOS_app_SF app* users receive the push message as expected. But, if the employee sends a message to the *PhotoShop_iOS_app_LA* app, because its VRSID Definition Segment is incorrect (`iOS` instead of `a.os contains "PhotoShop_iOS_app_LA"`), the message is sent to **all** iOS users in *AllAdobe PhotoShop_apps*. Although the message still goes to *PhotoShop_iOS_app_LA* users, the message also deny-lists the push IDs for *PhotoShop_iOS_app_SF* users because the *PhotoShop_iOS_app_SF* app has a different certificate. If the segment had been defined as `a.os contains “PhotoShop_iOS_app_LA”`, the push message would have been sent to only *PhotoShop_iOS_app_LA* users. 
  
If passed with the *PhotoShop_IOS_app_LA* push certificate, the push identifiers for the *PhotoShop_iOS_app_SF* come back as `invalid`.
  
>[!CAUTION]
>
>After you create a push message for an app that is using a VRS and click **[!UICONTROL Save & Send]**, an alert appears that reminds you ensure that each app that is listed **must** have a valid certificate. If each app does **not** have a valid certificate, your audience segments might be indefinitely deny listed, and you might not be able to send future push messages to the affected users. For more information about audience segments, see [Audience: define and configure audience options for push messages](/help/using/in-app-messaging/t-create-push-message/c-audience-push-message.md). 
