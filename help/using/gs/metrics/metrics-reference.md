---
description: Here is the reference information for the default mobile metrics and dimensions.
keywords: mobile
seo-description: Here is the reference information for the default mobile metrics and dimensions.
seo-title: Mobile Metrics and Dimensions Reference
solution: Marketing Cloud,Analytics
title: Mobile Metrics and Dimensions Reference
topic: Metrics
uuid: 96170ae7-8553-4f3e-ae01-65e5b664adf4
---

# Mobile metrics and dimensions reference {#mobile-metrics-and-dimensions-reference}

This information helps you understand more about the default mobile metrics and dimensions.

>[!TIP]
>
>The dimension and metric permissions that are set in Adobe Analytics apply to Mobile Services. When you try to run a report without the proper permissions, an error occurs.

## Metrics {#section_6704C815147D44AF96151D626BEB813C}

Here is the list of default mobile metrics:

* **First Launches**

  Triggered on the first run after an installation or a re-installation.

* **Upgrades**

  Triggered on the first run after an upgrade or when the version number changes.

* **Daily Engaged Users**

  Triggered when the application is used on a particular day.

  >[!TIP]
  >
  >The Daily Engaged Users event is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric.

* **Monthly Engaged Users**

  Triggered when the application is used during a month.
  
  >[!TIP]
  >The Monthly Engaged Users event is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric.

* **Launches**

  Triggered on a run that is not an install or an upgrade. This also triggers when the application is brought out of the background. By default, a new launch triggers when the application is in the background for five or more minutes. The amount of background time before triggering a new launch can be configured in **[!UICONTROL SDK Analytics Options]** on the Manage App Settings page. For more information, see the *Session Timeout (Seconds)* row in [Configure SDK Analytics Options](/help/using/c-manage-app-settings/c-mob-confg-app/t-config-analytics/t-config-analytics.md).
  
  >[!IMPORTANT]
  >Because how visits in [!UICONTROL Adobe Analytics] and mobile app launches in [!UICONTROL Adobe Mobile Services] are calculated, you might see different results in reporting. For more information, see [Compare Visits and Mobile App Launches](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html).

* **Crashes**

  Triggered when the application does not correctly exit. This event is sent when the application starts after a crash.
  
  >[!TIP]
  >The application is considered to crash if quit is not called.

* **Total Session Length**

  Aggregated total session length.

## Dimensions {#section_1784C7E859F64CCEB95C5DD1DCF5C98D}

Here is the list of default mobile dimensions:

* **Install Date**

  Date of the first launch after the installation. The date is in the *MM/DD/YYYY* format.

* **App ID**

  Stores the Application name and version in the following format: `[AppName] [BundleVersion]`. For example, `myapp 1.1`.

* **Launch Number**

  Number of times the application was launched or brought out of the background.

* **Days Since First Use**

  Number of days since the first run.

* **Days Since Last Use**

    Number of days since the last use.

* **Hour of Day**

  Measures the hour in which the app was launched and uses the 24-hour numerical format. This dimension is also used for time parting to determine peak usage times.

* **Day of Week**

  Number of the week day the app was launched.

* **Operating System**

  Operating system of the device.

* **Operating System Version**

  Operating system version.

* **Days Since Last Upgrade**

  Number of days since the application version number has changed.

  >[!TIP]
  >
  >Days since last upgrade is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting. 

* **Launches Since Last Upgrade**

  Number of launches since the application version number has changed.

  >[!TIP]
  >
  >Launches since last upgrade is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting. 

* **Device Name**

  Stores the device name. In iOS, a comma-separated, two-digit string identifies the iOS device. The first number represents the device generation, and the second number versions different members of the device family. For a complete list of common device names, see [iOS Device Versions](/help/ios/reference/device-versions.md).

* **Carrier Name**

  Stores the name of the mobile service provider.

* **Resolution**

  Width and height in actual pixels.
