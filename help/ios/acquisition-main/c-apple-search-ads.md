---
description: The Adobe SDK leverages Apple's Search Ads App Attribution APIs to enable developers and marketers to track and attribute app downloads that originate from Search Ads campaigns in the Apple App Store.
seo-description: The Adobe SDK leverages Apple's Search Ads App Attribution APIs to enable developers and marketers to track and attribute app downloads that originate from Search Ads campaigns in the Apple App Store.
seo-title: Apple Search Ads
solution: Experience Cloud,Analytics
title: Apple Search Ads
topic: Developer and implementation
uuid: 790080e8-067e-4bfd-a169-0027db4fdff3
---

# Apple Search Ads {#apple-search-ads}

The Adobe SDK leverages Apple's Search Ads App Attribution APIs to enable developers and marketers to track and attribute app downloads that originate from Search Ads campaigns in the Apple App Store. For more information about Search Ad campaigns, see [Apple Search Ads](https://searchads.apple.com).

## Benefits {#section_CEA30C652AC8470784B8054E299B80FA}

Here are some benefits to using Apple ads:

* Easily measure the effectiveness of your Search Ads app download campaigns by adding a few lines of code to your app. 
* Developers can access the date/time of the download and the bidded keyword that drove the conversion.

## Implementing Apple Ads {#section_F1094676793540CFA1DBB540174EEB6A}

>[!TIP]
>
>To implement Apple Ads, you must have iOS SDK version 4.13.2 or later.

To enable your app for Search Ad attribution:

1. Implement the Adobe SDK version 4.13.2 or above.

   For more information, see [Core implementation and lifecycle](/help/ios/getting-started/dev-qs.md). 

1. Add the iAd framework to the Xcode project file for your app.

## Reporting on Search Ads Attribution {#section_1AF4E0B4F8E94F36B38CA3D3E384D0A4}

1. Apple Search Ads attribution data is provided in the acquisition name, the source, and the term values.

   If attribution = `true`, all of the `iad-*` fields will be included in the lifecycle hit.

   In addition, the following values will be mapped from the `"iad"` dictionary to our typical acquisition context data fields:

    * `"iad-campaign-id"` --> `"a.referrer.campaign.trackingcode"`
    * `"iad-campaign-name"` --> `"a.referrer.campaign.name"`
    * `"iad-adgroup-id"` --> `"a.referrer.campaign.content"`
    * `"iad-keyword"` --> `"a.referrer.campaign.term"`

   This mapping ensures that the values are available in our standard reporting.
