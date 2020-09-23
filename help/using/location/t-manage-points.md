---
description: You can create and manage points of interest, which allow you to define geographical locations that you can use for correlation purposes, target with in-app messages, and so on. When a hit is sent in a point of interest, the point of interest is attached to the hit.
keywords: mobile
seo-description: You can create and manage points of interest, which allow you to define geographical locations that you can use for correlation purposes, target with in-app messages, and so on. When a hit is sent in a point of interest, the point of interest is attached to the hit.
seo-title: Manage Points of Interest
solution: Experience Cloud,Analytics
title: Manage Points of Interest
topic: Metrics
uuid: 7b362534-54fb-43a3-b6b2-dfc8f45ff7c6
---

# Manage points of interest {#manage-points-of-interest}

You can create and manage POIs, which allow you to define geographical locations that you can use for correlation purposes, target with in-app messages, and so on. When a hit is sent in a POI, the POI is attached to the hit.

Before you can use Location, verify the following requirements: 

* You must have Analytics—Mobile Apps or Analytics Premium. 
* You must enable **[!UICONTROL Location Reports]** for the app. 
* If you are using a version of the iOS SDK or Android SDK older than version 4.2, after adding new **[!UICONTROL Points of Interest]**, you must download a new configuration file and give it to your app developers.

  If you are using the iOS SDK or Android SDK version 4.2 or later, you do not need to submit an app update to the store to update your **[!UICONTROL Points of Interest]**. On the Manage Points of Interest page, when you click **[!UICONTROL Save]**, the changes are packaged to the **[!UICONTROL Points of Interest]** list and the configuration file for the live app is updated. Saving also updates the list of points in your app on the user devices, as long as the app uses the updated SDK and configuration with a remote POI URL.

On the user's device, for a hit to be assigned to a **[!UICONTROL Points of Interest]**, location must be enabled for the app. 

To use Location, complete the following tasks:

1. Click the name of the app to go to its Manage App Settings page.
1. Click **[!UICONTROL Location]** > **[!UICONTROL Manage Points of Interest]**.

   ![Step Result](assets/poi.png)

1. Type the information in each of the following fields:

    * **[!UICONTROL Point Name]**
  
      Type the **[!UICONTROL Point of Location]** name. 
  
      This could be the name of a city, county, or region. You can also create a **[!UICONTROL Point of Location]** around specific locations, such as sports stadiums or businesses.

    * **[!UICONTROL Latitude ]**

      Type the latitude of the **[!UICONTROL Point of Location]**. You can find this information from other sources, including the Internet.

    * **[!UICONTROL Longitude]**

      Type the longitude of the **[!UICONTROL Point of Location]**. You can find this information from other sources, including the Internet.

    * **[!UICONTROL Radius (Meters)]**

      Type the radius (in meters) around the **[!UICONTROL Point of Location]** that you want to include. For example, if you create a POI for Denver, Colorado, you can specify a radius large enough to include the city of Denver and the surrounding areas, but exclude Colorado Springs.

    * **[!UICONTROL Map Icon]**

      Select an icon that will display on the [Overview](/help/using/location/c-location-overview.md) and [Map](/help/using/location/c-map-points.md) reports.

1. Add additional POIs, as needed.

   We recommend that you add no more than 5,000 POIs. If you add more than 5,000, you can save the points, but you will receive a warning message informing you that best practices dictate having fewer than 5,000 points.

1. Click **[!UICONTROL Save]**.

To delete one or more POIs, select the applicable check boxes, and click **[!UICONTROL Remove Selected]**.

Click **[!UICONTROL Import]** or **[!UICONTROL Export]** to work with the data by using a `.csv` file instead of using the Adobe Mobile user interface.
