---
description: Beacon tracking allows you to measure and target micro locations by using iBeacon and Bluetooth Low Energy.
keywords: android;library;mobile;sdk
seo-description: Beacon tracking allows you to measure and target micro locations by using iBeacon and Bluetooth Low Energy.
seo-title: Beacon tracking
solution: Experience Cloud,Analytics
title: Beacon tracking
topic: Developer and implementation
uuid: 16c1d267-85f4-4a6a-a6d3-d6ffb0f80b29
---

# Beacon tracking {#beacon-tracking}

Beacon tracking allows you to measure and target micro locations by using iBeacon and Bluetooth Low Energy.

The following beacon data is sent to Analytics and Target when `trackBeacon` is called:

* `a.beacon.uuid` - ProximityUUID of the beacon 
* `a.beacon.major` - Major number of the beacon (such as store number) 
* `a.beacon.minor` - Minor number of the beacon (such as a unique number within a store) 
* `a.beacon.prox` - Values of 0-3 represent how close the user is to the beacon.

Here is what these values mean:

* 0 = unknown 
* 1 = immediate 
* 2 = near 
* 3 = far

This beacon data is captured in mobile solution variables.

## Track beacons {#section_FC3F213545944A468B1E6D5D5C8E2F1F}

1. Add the library to your project and implement lifecycle.

   For more information, see *Add the SDK and Config File to your IntelliJ IDEA or Eclipse Project* in [Core implementation and lifecycle](/help/android/getting-started/dev-qs.md). 

1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. Gather beacon location.

   Multiple third-party libraries are available to scan Bluetooth LE beacons, depending on the manufacturer of the beacon. 
1. After the beacon information has been obtained, use the following call to track the location: 

   ```java
   // assumed that the following variables will have been retrieved by the 3rd party beacon library 
   String beaconUUID; 
   String major; 
   String minor; 
   Analytics.BEACON_PROXIMITY proximity;  
   // BEACON_PROXIMITY is an enum available in the SDK. Number 0-3 representing how close the 
   // user is to the beacon. 0 unknown, 1 immediate, 2 near, 3 far.  
   Analytics.trackBeacon(beaconUUID, major, minor, proximity, null);
   ```

1. When the user leaves the beacon's proximity, clear the current beacon: 

   ```java
   Analytics.clearBeacon();
   ```

## Send additional data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the beacon data, you can send additional context data with each `trackBeacon` call:

```java
HashMap cdata = new HashMap<String, Object>(); 
cdata.put("myapp.ImageLiked", imageName); 
Analytics.trackBeacon(beaconUUID, major, minor, proximity, cdata);
```

Context data values must be mapped to custom variables in the Adobe Mobile services: 

![](assets/map-variable-context-ltv.png)

