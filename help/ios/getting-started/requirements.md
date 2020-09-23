---
description: Complete these steps to configure a report suite to collect iOS app data.
seo-description: Complete these steps to configure a report suite to collect iOS app data.
seo-title: Before You Start
solution: Experience Cloud,Analytics
title: Before You Start
topic: Developer and implementation
uuid: 04133f68-3618-41fd-8a13-aec5b6f04df6
---

# Before you start {#before-you-start}

Complete these steps to configure a report suite to collect iOS app data.

## Role-specific tasks {#section_8B9EA1FA189F4C6DB7D829F0B5844FBC}

Analytics administrators and app developers must complete the following tasks:

### Analytics administrators

To configure a report suite and collect mobile app data:

1. Complete one of the sections in [Log in to the Adobe Mobile Services UI](/help/ios/getting-started/getting-started.md). 
1. Create an Analytics account for each app developer.

App developers now have access to view the report suite(s) that you created.

>[!IMPORTANT]
>
>To create a new report suite and download the SDKs, you must be an Analytics Administrator.

### App developers

1. Ensure that your Analytics administrator has completed the steps in the *Analytics Administrators* section above. 

1. Verify that your Analytics administrator has completed one of the sections in the *Log in to the Adobe Mobile Services UI* below. 
1. After the report suite has been configured, complete steps in the *Download the SDK* section below.

For more information about roles and permissions, see [Roles and Permissions](/help/using/gs/c-mob-roles-and-permissions.md).

## Log in to the Adobe Mobile Services UI {#section_690A2EC4572E47869F183974E932A6A8}

Adobe Mobile services is the primary reporting interface for mobile app analytics and targeting. After you complete these steps you can download a configuration file that is pre-configured with your data collection server, report suite, and many other settings.

You can log in to the Adobe Mobile Services in one of the following ways:

* **Experience Cloud**

  Sign in to the [Experience Cloud](https://marketing.adobe.com) with your Adobe ID. 
  
  This method assumes that your company has been provisioned and you have linked your Analytics account. For more information about provisioning, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html). For more information about linking your account, see [Organizations and account linking](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html).

  >[!TIP]
  >
  >If you are unsure whether your company has been provisioned in the Experience Cloud, use your existing Adobe Analytics account.

* **Adobe Analytics**

  Click **[!UICONTROL Sign in with Analytics]** and enter your Analytics company name, your username, and your password.

## Create a report suite {#section_7BC602ED1ABA42C6AB722F506B5219F3}

To create a report suite to collect app data and define an app:

1. Click **[!UICONTROL Create New App]**.

   If you do not see this button, click **[!UICONTROL Manage Apps]** > **[!UICONTROL Add]**. 

1. In the **[!UICONTROL Report Suite]** drop-down, select **[!UICONTROL New Report Suite]**. 

1. Enter the name of your app and select a unique report suite ID.

   An example of a report suite ID is `mycomobileappdev`. You need to set up separate report suites and apps for the development and production versions. When you are ready to set up the production version, repeat these steps. 
1. Leave **[!UICONTROL Mobile App Template]** selected.

   This template enables timestamps to collect offline data and activates the mobile solution variables to capture lifecycle metrics. 

1. Select your **[!UICONTROL Timezone]**, your **[!UICONTROL Currency]**, and click **[!UICONTROL Save]**.

## Download the SDK {#section_044C17DF82BC4FD8A3E409C456CE9A46}

To download the mobile SDK:

1. Log in to Mobile Services and open your app in one of the following ways:

    * In the **[!UICONTROL All Apps]** drop-down list, select your app. 
    * On the right pane, find your app, and open it.

1. Click **[!UICONTROL Manage App Settings]**. 
1. In the **[!UICONTROL App SDK Downloads]** section, scroll to the **[!UICONTROL App SDK Downloads]** section. 

1. Download the SDK and the sample app for your platform.

>[!TIP]
>
>A config file for your app is automatically included in the SDK download, so you do not need to download that file separately. However, if you already downloaded the SDK, and you want to get updated settings, download the config file again.

