---
description: Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.
seo-description: Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.
seo-title: Target Preview on iOS
title: Target Preview on iOS
uuid: d92867a4-0569-4732-a928-28f9e2f8b21e
---

# Target Preview on iOS{#target-preview-on-ios}

Target Preview allows you to easily perform end-to-end QA for Target activities and preview these activities on your device.

For more information on how to set up and use Target Preview, see [Target Mobile Preview](https://docs.adobe.com/content/help/en/target/using/implement-target/mobile-apps/target-mobile-preview.html).

>[!IMPORTANT]
>
>To use Target Preview, you need SDK version 4.14.0 or later.

## Target Preview method

* **setPreviewRestartDeeplink**

  Sets an app deeplink that will be triggered when preview selections are applied in the Preview mode. 

  * Here is the syntax for this method:

    ```objective-c
     + (void) targetPreviewRestartDeepLink:(nullable NSString *)callbackURL;
    ```

  * Here is the code sample for this method:

    ```objective-c
    [ADBMobile targetPreviewRestartDeepLink:@" myapp://myhost"]; 
    ```
