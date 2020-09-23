---
description: The following table describes the different app identifiers that are used by the Android SDK and Adobe Mobile services.
seo-description: The following table describes the different app identifiers that are used by the Android SDK and Adobe Mobile services.
seo-title: App IDs
solution: Experience Cloud,Analytics
title: App IDs
topic: Developer and implementation
uuid: 3ac99489-6269-439e-a814-24102ef220b1
---

# App IDs{#app-ids}

The following table describes the different app identifiers that are used by the Android SDK and Adobe Mobile services.

 ID | Description |
|--- |--- |
|ID sent with lifecycle metrics|This is a combination of the app name and the bundle version that is submitted to the app store. This value is used for the  Versions report in Adobe Mobile services, and you can filter using this value to segment by a specific release version of your app.|
|App Store ID|This ID is assigned to your app by the app store and is provided in Adobe Mobile services when you create acquisition links.|
|AppID in ADBMobile JSON Config|This is a unique ID that is assigned to the app instance by Adobe Mobile services for all the associated metadata in the system. This ID is used to create the unique URLs for acquisition tracking or tracking link. This ID is automatically added to the ADBMobile JSON config file when this file is downloaded from the UI and can be found on  Manage App Settings under the Acquisition settings for your app.|