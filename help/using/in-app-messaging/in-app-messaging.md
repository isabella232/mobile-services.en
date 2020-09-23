---
description: Create, manage, and report on in-app and push messages.
keywords: mobile
seo-description: Create, manage, and report on in-app and push messages.
seo-title: Messaging
solution: Experience Cloud,Analytics
title: Messaging
topic: Metrics
uuid: e32d3e35-2d09-4ddf-8919-75dc895abcb3
---

# Messaging {#messaging}

You can create, manage, and report on in-app and push messages.

## New Adobe Experience Cloud SDK Release

Looking for information and documentation related to the Adobe Experience Platform Mobile SDK? Click [here](https://aep-sdks.gitbook.io/docs/) for our latest documentation.

As of September 2018, we released a new, major version of the SDK. These new Adobe Experience Platform Mobile SDKs are configurable through [Experience Platform Launch](https://www.adobe.com/experience-platform/launch.html).

* To get started, go to [Launch](https://launch.adobe.com/).
* To see what is in the Experience Platform SDK repositories, go to [Github: Adobe Experience Platform SDKs](https://github.com/Adobe-Marketing-Cloud/acp-sdks).

>[!IMPORTANT]
>
> If you are using the Adobe Experience Platform Mobile SDKs with Adobe Launch, you **must** also install the Adobe Analytics Mobile Services extension to use Adobe Mobile Services features such as Acquisition links. For more information see [Adobe Analytics - Mobile Services](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics-mobile-services). For information about using push messaging and in-app messaging with the Experience Platform SDKs, see [Set up push messaging](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics-mobile-services#set-up-push-messaging) and [Set up in-app messaging](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics-mobile-services#set-up-in-app-messaging).

## In-app messages {#section_8984F4568BC24D32A87429FFCB5184A6}

In-app messages are delivered to users in real-time, based on their actions and traits. The messages are triggered from Analytics data already tracked by the SDK.

The following message types are supported:

* Custom and themed 
* Full screen 
* Native alerts 
* Local notifications

To help you understand how in-app messaging works, here is some additional information:

* In-app messages require SDK version 4.2 or later. 
* You must specify who has Mobile App Admin rights.

  These rights enable access to acquisition links and in-app messages. For more information, see [Roles and permissions](/help/using/gs/c-mob-roles-and-permissions.md). 
* After a message is approved, the message is published automatically to the application. 
* The SDK presents the message to users when the message parameters, such as traits, trigger, and schedule, are met. 
* Messages can contain custom HTML or an image, using an online URL.

    A backup or alternative image from the app bundle can also be specified for messages that are triggered while offline. 
* Active and completed messages provide reports on total views, click-through rates, and so on. 
* Templates are available for custom messages, which allows you to easily build your own in-app message.

## Push messages {#section_90555A55BCE7427A90B1577E14BEF51B}

Push messages are sent to users who have opted in to receive notifications. You can target these push messages to users in Analytics segments or custom segments. You can use push messages to re-engage passive users or to convey time-specific and location-specific information because the messages appear outside your app.

Before you can configure push messaging, see [Prerequisites to enable push messaging](/help/using/c-manage-app-settings/c-mob-confg-app/configure-push-messaging/prerequisites-push-messaging.md). After you perform these tasks, you must configure push messaging in your app's settings. For more information, see [Configure push messaging](/help/using/c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-push-messaging.md).
