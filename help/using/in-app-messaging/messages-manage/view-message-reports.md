---
description: You can view message reports for in-app and push messages.
keywords: mobile
seo-description: You can view message reports for in-app and push messages.
seo-title: View message reports
solution: Marketing Cloud,Analytics
title: View message reports
topic: Metrics
uuid: 0ac73a81-388f-4dfd-84d5-21b8db4b8c83
---

# View message reports{#view-message-reports}

You can view message reports for in-app and push messages.

1. Click ![report icon](assets/icon_report.png) in the **[!UICONTROL Report]** column for a message.
1. (**Optional**) Create a sticky filter for the report or change the time period by clicking the **[!UICONTROL Calendar]** icon.

    For more information about creating a sticky filter, see [Add a sticky filter](/help/using/usage/reports-customize/t-sticky-filter.md).

>[!TIP]
>
>Depending on the type of message you are viewing, the report might vary.

## In-app messages {#section_90B79BA58E8141F78538C187EB1BF8C7}

If you are viewing reports for an in-app message, the report looks similar to the following illustration:

![report message](assets/report_message.png)

### In-app message metrics

Here is a list of the metrics that are available for in-app messages:

* **[!UICONTROL Impression]**, when a message is triggered.

* **[!UICONTROL Click through]**, when a user presses the **[!UICONTROL Click Through]** button on an alert or full-screen message, and when a user opens the app from a local notification.

* **[!UICONTROL Cancel]**, when a user presses the **[!UICONTROL Cancel]** button on an alert or a full-screen message.

* **[!UICONTROL Engagement Rate]**, a calculated metric from Adobe Analytics and is the result of the number of click throughs divided by the number of impressions.

## Push messages {#section_BEAFD858CA194185B6F88903446058E9}

If you are viewing reports for a push message, the report looks similar to the following illustration:

![push message](assets/report_message_push.png)

The chart at the top displays the number of users who opened the message.

### Push message metrics

Here is a list of the metrics that are available for push messages:

* **[!UICONTROL Time]**

  The time the message was pushed to devices from Mobile Services.

* **[!UICONTROL Status]**

  The status of the message, and the available statuses are:

  * **[!UICONTROL Cancelled]**
  * **[!UICONTROL Scheduled]**
  * **[!UICONTROL Executing]**
  * **[!UICONTROL Executed]**

* **[!UICONTROL Published]**

  The number of device tokens successfully sent to Apple Push Notification Service/Firebase Cloud Messaging (APNS/FCM) for sending the message to the users devices.

* **[!UICONTROL Failed]**

  The number of device tokens not successfully sent to APNS/FCM. Some possible reasons for failures:

  * An invalid pushID

  * The push platform (APNS, FCM, and so on) that was given to push to does not exist for the job's application. For example, the platform might collect iOS push tokens but does not have APNS service configured.

  * The message might have failed because the push service was not configured correctly or the Mobile Services system is down.  

  >[!IMPORTANT]
  >
  >If you have an unusually large number of failures, check your push services configuration. If push services appears to be configured correctly, contact Adobe Customer Care.

* **[!UICONTROL Blocklisted]**

  The number of device tokens that are no longer valid to be sent to APNS or FCM. This usually means the app has been uninstalled from the device or the user changed his or her opt-in settings to receive messages. Android and iOS differ about when tokens are counted as blocklisted. Android tokens are immediately shown in the blocklist count. iOS tokens are initially displayed as published, but based on feedback from APNS, are shown as blocklisted on subsequent messages.
