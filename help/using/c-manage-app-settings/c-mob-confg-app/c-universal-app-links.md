---
description: Universal Links (iOS) and App Links (Android) allow you to connect to deep links in your iOS or Android apps.
keywords: mobile
seo-description: Universal Links (iOS) and App Links (Android) allow you to connect to deep links in your iOS or Android apps.
seo-title: Apple Universal Links and Android App Links
solution: Experience Cloud,Analytics
title: Apple Universal Links and Android App Links
topic: Metrics
uuid: 8d6441dc-4307-4454-95ea-d77ec796f918
---

# Apple Universal Links and Android App Links{#universal-links-and-app-links}

Universal Links (iOS) and App Links (Android) allow you to connect to deep links in your iOS or Android apps.

>[!IMPORTANT]
>
>Starting with iOS 9.2, deep linking is not supported. You must use Apple Universal Links for deep linking to your app or website.

## Universal Links {#section_F8147944679A42E59CF4FD8814E5EF12}

Universal Links allow you to connect to deep links in your iOS app and are supported in iOS 9.2 or later. When a Universal Link is accessed, iOS redirects the link directly to the deeplink in your app. If your app is not installed, it opens a URL for your website in a browser instead. For more information about Universal Links, see [Support Universal Links](https://developer.apple.com/library/content/documentation/General/Conceptual/AppSearch/UniversalLinks.html).

## App Links

App Links allow you to connect to deep links in your Android app and is supported in Android 6.0 or later. When an App Link is accessed, Android redirects the link directly to the deeplink in your app. If your app is not installed, it opens a URL for your website in a browser instead. For more information about App Links, see the [Handling Android App Links](https://developer.android.com/training/app-links/index.html).

## Create a Marketing Link by using a Universal or App Link {#section_609ADEFFB9B441C4A8C45E936D0DC859}

You can create a Marketing Link that uses a Universal or App Link.

### Configure a Universal Link

1. To set up Universal Links in your iOS app, go to [Handling Universal Links in Apple](https://developer.apple.com/documentation/uikit/inter-process_communication/allowing_apps_and_websites_to_link_to_your_content/handling_universal_links).

2. In Adobe Mobile Services, set up the site-association documents:

    a. In the Mobile Services home page, select the app for which you want to set up Universal Links.

    b. Click **[!UICONTROL Manage App Settings]**.

    c. Ensure the iOS app that handles the Universal Links is added to the **[!UICONTROL Add App Store Apps]** section.

    >[!TIP]
    >
    >If the **[!UICONTROL Add App Store Apps]** section does not display, click the **[!UICONTROL Add App Store App]** link.

    d. In the **[!UICONTROL Universal Links and App Links Options]** section, select an iOS app and type the App ID.

    f. Click **[!UICONTROL Save]**.

    You must provide at least one iOS app selection and one App ID, or you will receive an error.

    >[!IMPORTANT]
    >
    >You can update the documents by clicking Update from the Universal Links and App Links Options section. However, when you click **[!UICONTROL Update]**, a warning notifies you that all Universal Links or App Links that you created in the past will be affected.

### Use a Universal Link

1. In Adobe Mobile Services, create a Marketing Link that uses Universal Links:

    a. Select the app from the Mobile Services home page, click **[!UICONTROL Acquisition]** > **[!UICONTROL Marketing Link Builder]**.

    b. Click **[!UICONTROL Create New]**.

    c. Under **[!UICONTROL Marketing Link Options]**, select **[!UICONTROL Use Universal Links or App Links]**.

    d. If you configured the site-association documents in the *Setting up site-association documents in Adobe Mobile Services* section above, this option is selected by default. 

    If you did not configure the documents, the **[!UICONTROL Use Universal Links or App Links]** option is disabled and **[!UICONTROL Use Interstitials]** is selected by default.

    e. If the **[!UICONTROL Use Universal Links or App Links]** option is selected, the **[!UICONTROL Custom Path]** field is displayed. 

      This allows users to define the URL path after the domain with any query parameter. For example, if you type `my/universal/link?os=9.2`, your full Marketing Link URL becomes `https://[marketing link domain]/my/universal/link?[AMS default query parameters]&os=9.2`.

    f. Click the **[!UICONTROL Decisions]** tab and configure your decision tree.

    h. If the iOS app is installed, the app handles the deeplink with its logic. The final destination serves only as the fallback when the app is not installed. Since the app is not installed, the final destination can only be a web link or app store.

    i. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Once a Marketing Link is saved, the Marketing Links Options cannot be altered. This is because you do not want to change the behavior of the Marketing Links that may have already been distributed.


### Configure an App Link

1. To set up App Links in your Android app, go to [Add Android App Links](https://developer.android.com/studio/write/app-link-indexing).

1. In Adobe Mobile Services, set up the site-association documents:

    a. In the Mobile Services home page, select the app for which you want to set up App Links.

    b. Click **[!UICONTROL Manage App Settings]**.

    c. Ensure the Android app that handles Universal Links or App Links is added to the **[!UICONTROL Add App Store Apps]** section.

    >[!TIP]
    >
    >If this section does not display, click the **[!UICONTROL Add App Store App]** link.

    d. Scroll to the **[!UICONTROL Universal Links and App Links Options]** section.

    e. Click the **[!UICONTROL App Links (Android)]** tab.

    f. Select an Android app and type a SHA-256 certificate fingerprint.

    g. Click **[!UICONTROL Save]**.
    
      You must provide at least one Android app selection and one SHA-256 certificate, or you will receive an error.

    >[!IMPORTANT]
    >
    >You can update the documents by clicking **[!UICONTROL Update]** from the **[!UICONTROL Universal Links and App Links Options]** section. However, when you click **[!UICONTROL Update]**, a warning notifies you that all Universal Links or App Links that you created in the past will be affected.

### Use an App Link

1. In Adobe Mobile Services, create a Marketing Link that uses App Links:

    a. Select the app from the Mobile Services home page, click **[!UICONTROL Acquisition]** > **[!UICONTROL Marketing Link Builder]**.

    b. Click **[!UICONTROL Create New]**.

    c. In the **[!UICONTROL Marketing Link Options]** section, select **[!UICONTROL Use Universal Links or App Links]**.

    d. If you configured the site-association documents from step 2, this option is selected by default. 

      If not, the **[!UICONTROL Use Universal Links or App Links]** option is disabled, and **[!UICONTROL Use Interstitials]** is selected by default.

    e. If **[!UICONTROL Use Universal Links or App Links]** is selected, the **[!UICONTROL Custom Path]** field is displayed. 

      This allows users to define the URL path after the domain with any query parameter. For example, if you type `my/app/link?os=6.0`, your full Marketing Link URL becomes `https://[marketing link domain]/my/app/link?[AMS default query parameters]&os=6.0`.

    f. Click the **[!UICONTROL Decisions]** tab and configure your decision tree.

    g. If the Android app is installed, the app handles the deeplink with its logic. 

      The final destination serves only as the fallback case for when the app is not installed. Since the app is not installed, the final destination can only be a web link or app store.

    h.  Click **[!UICONTROL Save]**.

>[!TIP]
>
>After a Marketing Link is saved, the **[!UICONTROL Marketing Links Options]** cannot be altered. This is because you do not want to change the behavior of the Marketing Links that may have already been distributed.

## Using Marketing Links

You can now use these Marketing Links in messaging and other areas in your app.

>[!IMPORTANT]
>
>You will not see click tracking counts with Universal Links or App Links, and you can also not use interstitials. 

