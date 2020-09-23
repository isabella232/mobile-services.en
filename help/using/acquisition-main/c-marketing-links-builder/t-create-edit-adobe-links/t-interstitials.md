---
description: You can route users to a destination depending on whether they have the app installed (an app deep link) or not installed (to a website or an app store).
keywords: mobile
seo-description: You can route users to a destination depending on whether they have the app installed (an app deep link) or not installed (to a website or an app store).
seo-title: Interstitials
solution: Experience Cloud,Analytics
title: Interstitials
topic: Metrics
uuid: 7dce8ab2-2a5d-4384-ac1e-e31dfaa33654
---

# Interstitials{#interstitials}

You can route users to a destination depending on whether they have the app installed (an app deep link) or not installed (to a website or an app store). The choice of routing is best left to users. Marketers can provide user choices by configuring an interstitial page that shows users the available landing destinations.

To configure an interstitial when creating a Marketing Link:

1. Click **[!UICONTROL Edit Deep Link Interstitial]**.

   ![Deep link interstitial](assets/interstitial2.png)

1. Type information in the following fields:

   * **[!UICONTROL Custom HTML]**

      Select your custom interstitial HTML page. 
  
      By using custom interstitials, marketers can customize interstitial landing pages with custom HTML/CSS/JS, which allows you to brand your pages. 

      Here are the requirements for the HTML page: 

      * Must be an HTML file.  
      * Must contain the `%%DEST%%` and `%%FALLBACK%%` placeholders.
      * The uploaded HTML will be served in an `<iframe>`. 

        You must ensure that your link targets are pointing to a parent window. You can include `<base target="_parent" />` in `<head>` or specify a target property for each `<a/>` individually.  

        >[!TIP]
        >
        >If you upload custom HTML, the other four options in this table will not be used unless you remove the uploaded file.

   * **[!UICONTROL Image URL]**

      Specify the URL to an image asset.

   * **[!UICONTROL Body Text]**

     Specify the body text for the interstitial.

   * **[!UICONTROL Confirm Text]**

      Specify the text for the text button.

   * **[!UICONTROL  Fallback Text]**

      Specify the fallback text to display.

      This field updates the text button if a deep link fails. Users are directed to try the deep link before allowing them to fall back to another option. For example, a fallback could be to an app store to download and install the app or take users to the company's website. The fallback text lets users know that there is another option available if the deep link fails.

1. (**Optional**) Click the icons above the image to see how the interstitial looks rotated and on different devices.

   You can change or edit the image outside Mobile Services to ensure that the image displays properly in different situations.
1. Click **[!UICONTROL Save]**.
