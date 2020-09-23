---
description: You can use this information to create a new app and configure its key metrics;configure the SDK options for Adobe Analytics and Adobe Audience Manager;configure acquisition and ID service options;and download the configuration file, SDKs, and developer and tester tools.
keywords: mobile
seo-description: You can use this information to create a new app and configure its key metrics;configure the SDK options for Adobe Analytics and Adobe Audience Manager;configure acquisition and ID service options;and download the configuration file, SDKs, and developer and tester tools.
seo-title: Add a New App
solution: Experience Cloud,Analytics
title: Add a New App
topic: Metrics
uuid: 706b5e4d-1318-4a9e-8c69-ffabf51fa02c
---

# Add a new app{#add-a-new-app}

You can use this information to create a new app and configure its key metrics;configure the SDK options for Adobe Analytics and Adobe Audience Manager; configure acquisition and ID service options; and download the configuration file, SDKs, and developer and tester tools.

 These instructions will help you add a new app and configure Adobe Analytics and Adobe Audience Manager integrations.

Before you can configure your app, you must add it in the Adobe Mobile Services user interface. After you create the app, the correct configuration is generated, and you can provide this configuration to the developers who are implementing the Mobile SDK for the app. 

1. Sign in to Adobe Mobile Services and complete one of the following tasks:

    * Click **[!UICONTROL Create New]** to create an app. 
    * To add additional apps, click Manage Apps in the left navigation menu and click **[!UICONTROL Add]**.

      For more information about signing in, see [Sign in](/help/using/gs/gs-signin.md).

      >[!TIP]
      >
      >To manage existing apps, click Manage Apps in the left navigation menu and click the app that you want to modify. You can make changes on the App Information page.

1. Type information in the following fields:

   **[!UICONTROL Report Suite]**

     Specify the report suite in which reporting data will be collected and stored in Adobe Analytics. Each app is connected to one Analytics report suite. If you are sending app data to multiple reports suites, add a new app for each report suite. Each app is connected to one Analytics report suite. If you are sending app data to multiple reports suites, add a new app for each report suite.

     If you have been given Analytics administrator privileges in Adobe Mobile, you can create a new report suite in Adobe Mobile. To create a new report suite, select **[!UICONTROL New Report Suite]** and type information into the following fields:

      * **[!UICONTROL Report Suite ID]**

        This ID uniquely identifies the report suite in Adobe Analytics. Your company prefix is automatically added to the beginning of the ID.  

      * **[!UICONTROL Copy Settings From]**

        The variables, events, processing rules, and other settings are set up in the new report suite exactly like they are in this report suite. A report suite created in Mobile Services is offline-enabled (or time stamped) only if the **[!UICONTROL Copy Settings From]** report suite used was the Mobile App Template, or if you create a report suite that is offline enabled.

      * **[!UICONTROL Timezone]**

        All reporting dates are in this time zone. This setting attempts to use a time zone close to what your browser uses.

      * **[!UICONTROL Currency]**
 
        Revenue is tracked and reported as this type of currency.

      >[!TIP]
      >
      >To use a virtual reporting suite (VRS), see [Virtual Report Suites](/help/using/manage-apps/c-mob-vrs.md).  

   * **[!UICONTROL Icon]**

      (**Optional**) To browse to and select an icon for your app, click **[!UICONTROL Icon]**.

   * **[!UICONTROL Name]**

      (**Optional**) Type a descriptive name for the app. This name helps you quickly locate an app, and a meaningful name can help you quickly understand the app's purpose and settings.

   * **[!UICONTROL Type]**

      Select a type from the drop-down list. The available reports that display in the left navigation menu vary depending on the type of app you select.

      Here are the available types:

      * **[!UICONTROL Standard]**

           You can leave the **[!UICONTROL Standard]** option selected for most apps.

      * **[!UICONTROL Publication]**

          You can select this option if your app was built using Adobe Digital Publishing Suite.

      * **[!UICONTROL Game]**

        This option is similar to the **[!UICONTROL Standard]** option, except that **[!UICONTROL Game]** updates the terminology used in the reports to terms for games. For example, users is changed to players. Game-specific reports are automatically shown for game apps.

   * **[!UICONTROL Description]**

      (**Optional**) Type a description for the app.

1. Click **[!UICONTROL Save]** to add the new app.

   After the app has been added, you can check the App Information page about configuring additional options. For more information, see [Manage App Settings](/help/using/c-manage-app-settings/c-manage-app-settings.md).
