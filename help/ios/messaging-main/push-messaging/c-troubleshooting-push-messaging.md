---
description: This information helps you troubleshoot push messaging.
keywords: mobile
seo-description: This information helps you troubleshoot push messaging.
seo-title: Troubleshooting Push Messaging
solution: Experience Cloud,Analytics
title: Troubleshooting Push Messaging
topic: Metrics
uuid: 87d7dcb6-82a8-46e3-a6ed-7f895a22f2af
---

# Troubleshooting push messaging {#troubleshooting-push-messaging}

This information helps you troubleshoot push messaging.

## Why are there sometimes delays sending push messages?

The following types of delays might be associated with push messages for Mobile Services:

* **Waiting for Analytics Hits**

  Every report suite has a setting to determine when to process incoming Analytics hits. The default is 1 hour on the hour. The actual processing of Analytics hits might take up to 30 minutes but is typically 15-20 minutes.
  
  For example, a report suite processes hits every hour. If you factor in the processing time of a maximum of 30 minutes, it could take up to 90 minutes for an incoming hit to be available for a push message. If a user launched the app at 9:01 AM, the hit would show up in the Mobile Services UI as a new unique user between 10:15 to 10:30 AM.

* **Waiting for Push Service**
  
  The push service (APNS or GCM) might not immediately send out the message. Although uncommon, we have seen a delay of 5-10 minutes. On the Messages page, you can verify that the push message has been sent to the push service by clicking the View link for the message. In the report, the number of successful sends to the push service is listed in the Published column.
  
  >[!TIP]
  >
  >The push services do not guarantee a message will be sent. For more information about the reliability of services, see the appropriate documentation:
  >
  >* **APNS**: [Quality of Service](https://developer.apple.com/documentation/usernotifications)
  >
  >* **GCM**: [Lifetime of a Message](https://developers.google.com/cloud-messaging/concept-options)

## How do I renew my Apple Push Service Certificate?

Sending push messages requires a valid Push Service Certificate. Mobile Services will notify you when your certificate is close to expiring or has expired. If you receive this notification, complete the following steps to renew your certificate:

  1. Click **[!UICONTROL Manage App Settings]**.
  2. To delete the current certificate, scroll to **[!UICONTROL Push Services]** and click **[!UICONTROL Delete]**.
  3. Configure and test a new certificate.

     For more information, see [Prerequisites to Enable Push Messaging](/help/using/c-manage-app-settings/c-mob-confg-app/configure-push-messaging/prerequisites-push-messaging.md)

  4. Click **[!UICONTROL Save]**.

## Why can't I see my push messages in an iOS simulator?

  iOS simulators do not support push messaging.
