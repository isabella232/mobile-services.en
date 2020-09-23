---
description: You can create Marketing Links to acquire new mobile app users on-the-fly by manually configuring the URL parameters.
keywords: mobile
seo-description: You can create Marketing Links to acquire new mobile app users on-the-fly by manually configuring the URL parameters.
seo-title: Manually create Acquisition links
solution: Experience Cloud,Analytics
title: Manually create Acquisition links
topic: Metrics
uuid: d7709203-f793-4982-adaa-9c3c914aca2b
---

# Manually create Acquisition links {#create-acquisition-link-manually}

You can create Marketing Links to acquire new mobile app users on-the-fly by manually configuring the URL parameters.

>[!IMPORTANT]
>
>This feature requires SDK version 4.6 or later. For more information, see [Acquisition prerequisites](/help/using/acquisition-main/c-acquisition-prerequisites.md).

The following diagram illustrates the components of a manually built tracking link and displays the different URL parameters that you must properly configure when manually creating acquisition links.

![](assets/acquisition_url.png)

This link is configured to perform a platform-specific redirect to the Google Play store or the Apple App Store for a mobile app. If the destination cannot be determined, the default store has been set to the Apple App Store. After the app has been installed, the `my.custom.key:test` custom context key is attached to the Analytics Install Hit.

To manually create links, use the following URL format:

`http(s)://c00.adobe.com/v3/ {mobile-services-app-hash}/start? {parameters}`

>[!TIP]
>
>The version of Android SDK you are using has no impact on this process.

For iOS, ensure that you use the correct protocol:

* Use **HTTP** if you are using the iOS SDKs before version 4.7.0, or if you are using iOS SDK 4.7.0 or later, and if **[!UICONTROL Use HTTPS]** is **not** selected on the Manage App Settings page. 
* Use **HTTPS** if you are using iOS SDK 4.7.0 or later and **[!UICONTROL Use HTTPS]** **is** selected on the Manage App Settings page.

Where the following conditions have been met:

* `{mobile-services-app-hash}` matches the application identifier in the configuration `acquisition:appid ` file.

  You can locate `{mobile-services-app-hash}` in the Manage App Settings page under Acquisition SDK Options in the Tracking ID field.

  ![](assets/tracking-id.png)

* `{parameters}` is a list of standard specifically named URL query parameters.

Here is the list of parameters:  

* **`a_g_id`**

  Google Play Store App Identifier.

  * Sample value: `com.adobe.beardcons`

* **`a_g_lo`**

  Google Play Store Locale Override.

  * Sample value: `ko`

* **`a_i_id`**

  iTunes App Identifier.

  * Sample value: `835196493`

* **`a_i_lo`**

  iTunes Locale Override.

  * Sample value: `jp`

* **`a_dd`**

  Default Store for Auto Redirect.

  * Sample value: `i | g`

* **`a_cid`**

  Custom ID Override (generally IDFA for iOS or ADID for Android).

  * Sample value: `Any String < 255 characters (UTF-8 encoded)`

* **`ctx*`**

  Keys prefixed with `ctx` will be in the context data of the resulting launch hit.

  * Sample value: `ctxmy.custom.key=myValue`

* **`ctxa.referrer.campaign.name`**

  Acquisition Campaign Name.
  
  This parameter is required for reporting if you want to compare the performance of different acquisition links. 

  * Sample value: 2015 Summit Conference

* **`ctxa.referrer.campaign.trackingcode`**

  Tracking Code
  
  This parameter is required for reporting if you want to compare the performance of different acquisition links. 

  * Sample value: `lexsxouj`

* **`ctxa.referrer.campaign.source`**

  The source.

  * Sample value: Ad Network

* **`ctxa.referrer.campaign.medium`**

  Medium

  * Sample value: Email

* **`ctxa.referrer.campaign.content`**

  Content

  * Sample value: Image # 325689

* **`ctxa.referrer.campaign.term`**

  Term

  * Sample value: hiking+boots


When you manually create acquisition links, remember the following information:

* All parameters that do not match parameters in the table are passed on as part of the app store redirect. 
* All parameters are technically optional, although the link will be nonfunctional, if at least one store ID is specified.

  An example of a store ID is `a_g_id`/ `a_i_id`. 

* If the destination store cannot be automatically determined, and no default is provided, an 404 error is returned.

