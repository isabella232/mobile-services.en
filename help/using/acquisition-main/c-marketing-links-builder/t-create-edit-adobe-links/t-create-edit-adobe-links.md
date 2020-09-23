---
description: You can create or edit Marketing Links to provide deep linking into your mobile app or your website.
keywords: mobile
seo-description: You can create or edit Marketing Links to provide deep linking into your mobile app or your website.
seo-title: Create or Edit Marketing Links
solution: Experience Cloud,Analytics
title: Create or Edit Marketing Links
topic: Metrics
uuid: 305a8265-38de-4d19-8c79-b3912f5aae7c
---

# Create or edit marketing links{#create-or-edit-marketing-links}

You can create or edit Marketing Links to provide deep linking to your mobile app or your website. For more information, see [Apple Universal Links and Android App Links](/help/using/c-manage-app-settings/c-mob-confg-app/c-universal-app-links.md).

1. In your app, in the left navigation pane, expand **[!UICONTROL Acquisition]** and click **[!UICONTROL Marketing Link Builder]**.
1. Complete one of the following tasks:

    * To create a Marketing Link, click **[!UICONTROL Create New]**.
    * To edit a link, click the link's name in the **[!UICONTROL Title]** column.

1. Type information in the following fields:

    * **[!UICONTROL Marketing Link Name]**:

      (**Required**) Specify a descriptive name for your Marketing Link. The name displays only on the Marketing Links page in the Adobe Mobile Services UI. A descriptive name helps you or others in your organization quickly find a specific link and can provide insight into its purpose.

    * **[!UICONTROL Unique Tracking Code]**:

      (**Required**) Specify the desired tracking code or click (![generate icon](assets/icon_generate.png) to create a new tracking code. You can view reports that detail use of the tracking code.

    * **[!UICONTROL Add Tracking Context Data]**:

      (**Optional**) Click the **[!UICONTROL +]** icon and type the relevant information to track your campaign using context data. In the **[!UICONTROL Custom Context Data]** drop-down list, select a preset tag or one of your own tags. Context data is used for reporting when the Marketing Link is deployed.

      The following preset tags are available:

      * **Custom Context Data**
        Specify the key and value. If you add custom context data, you must create a processing rule. For more information, see [Processing rules overview](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html).

      * **Source**
        Specify the original referrer, such as "newsletter" or "homepage."

      * **Medium**
        Specify the marketing medium, such as "banner" or "email."

      * **Content**
        Specify the name or ID of the ad with the link.

      * **Term**
        Specify paid terms or other search terms for the ad.
1. Click **[!UICONTROL Save]**.
1. Type information in the following fields:

    * **(Required)** In **[!UICONTROL Fallback URL]**, specify the URL that users are directed to when a destination cannot be matched (for example, if the user is on a desktop or another platform that does not match a destination rule).
    * In **[!UICONTROL Marketing Link Options]**, select **[!UICONTROL Interstitials]** or **[!UICONTROL Universal and App Links]**.

      For more information, see [Interstitials](/help/using/acquisition-main/c-marketing-links-builder/t-create-edit-adobe-links/t-interstitials.md) or [Apple Universal Links and Android App Links](/help/using/c-manage-app-settings/c-mob-confg-app/c-universal-app-links.md).

    * **(Conditional)** If **[!UICONTROL Universal or App Links]** is selected, in **[!UICONTROL Custom Path]**, users can define the URL path after the domain with any query parameter. For more information, see [Apple Universal Links and Android App Links](/help/using/c-manage-app-settings/c-mob-confg-app/c-universal-app-links.md).

1. Click **[!UICONTROL Edit Deep Link Interstitial]** and configure the link.

   (**Optional**) When there are multiple destinations, users can be routed depending on whether they have a mobile app installed. If the app is installed, an interstitial landing page is displayed.

   For more information, see [Interstitials](/help/using/acquisition-main/c-marketing-links-builder/t-create-edit-adobe-links/t-interstitials.md). 

1. Click **[!UICONTROL Save]** and click **[!UICONTROL Next]**.
1. In the Destination page, configure the link.

   1. Click the **[!UICONTROL Decision]** icon (![decision icon](assets/icon_decision.png)) and select one of the following decision locations:

      * **[!UICONTROL Add Decision]**
      * **[!UICONTROL Add Path]**

   1. If you selected **[!UICONTROL Add Decision]**, select one of the following decision types:

      * **[!UICONTROL Operating Decision]**

        Supported operating systems include iOS, Android, AMX, and so on. 

      * **[!UICONTROL Device Type]**

        Device types include devices such as desktops, eReaders, game consoles, mobile phones, set top boxes, and so on.

   1. Click the **[!UICONTROL Destination]** icon ( ![square icon](assets/icon_square.png) ) and select one of the following destination types:

      * **[!UICONTROL App Store]**
      * **[!UICONTROL Web Link]**
      * **[!UICONTROL App Deep Link]**
      * **[!UICONTROL Hybrid Link]**

      >[!TIP]
      >
      >When you use the **[!UICONTROL Web Link]** destination type with a link to the app store, acquisition is not tracked. To track acquisitions, use the **[!UICONTROL App Store]** destination type.

      For more information, see [Create a new link destination](/help/using/acquisition-main/c-manage-link-destinations/t-create-new-app-deep-link-destination.md).

1. To save the Marketing Link, click ![elipses](assets/icon_elipses.png) and then **[!UICONTROL Save]**.
