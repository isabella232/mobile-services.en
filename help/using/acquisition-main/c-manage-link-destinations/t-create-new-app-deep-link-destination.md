---
description: You can create a new link destination that directs users to a web or a deep link in your app.
keywords: mobile
seo-description: You can create a new link destination that directs users to a web or a deep link in your app.
seo-title: Create New Link Destination
solution: Experience Cloud,Analytics
title: Create New Link Destination
topic: Metrics
uuid: 390e3dea-0221-4f97-980d-a90ca9f162fa
---

# Create a new link destination {#create-new-link-destination}

You can create a new link destination that directs users to a web or a deep link in your app.

1. In the Mobile Services UI, click **[!UICONTROL Manage Apps]**.
1. Click the name of the app to display its App Information page.
1. Click **[!UICONTROL Manage Link Destinations]**.
1. Click **[!UICONTROL Create New]**.
1. Type information in the following fields:
    * **[!UICONTROL Title]**

      Type a descriptive name for your App Link destination. The title displays only on the Manage Link Destinations page in the Adobe Mobile Services UI. A descriptive name helps you or others in your organization quickly find a specific link destination and can provide insight into its purpose.

    * **[!UICONTROL Link Type]**

      Here is a list of the available link types:
  
      * **[!UICONTROL App Deep Link]**
  
        Provide a URI schema deep link (for example, `yourapp://section`). App deep link destinations are URI schema deep links that direct users to a deep link in your app. For example, you can direct users to a specific product line in an online retailer's mobile app.
  
      * **[!UICONTROL Web Link]**  
  
        Type a web HTTP or HTTPS URL, for example,`https://adobe.com`. Web link destinations direct users to a URL. For example, you can direct users to a product line on an online retailer's website.
  
      * **[!UICONTROL Hybrid Link]**

        Type an iOS Universal Link or an Android App Link (for example, `https://yourwebsite.com`). Hybrid links support iOS Universal Links or Android App Links.
  
    * **[!UICONTROL App]**
      Select the app that is associated with the link you are going to provide.
  
      >[!TIP]
      >
      >This information is required only if you selected an App Deep Link or a Hybrid Link in **[!UICONTROL Link Type]**. If the app does not appear in the selection list, click **[!UICONTROL Add New App]** to reference a new app from an app store. 

    * **[!UICONTROL Link type]**
  
      Type the actual URL for the link you selected. The label of this field will vary depeneding on the type of link you selected. 

    * **[!UICONTROL Notes]**
  
      Type optional notes for your destination. Additional notes display only on the Manage Link Destinations page in the Adobe Mobile Services UI. Additional notes can help you or others in your organization quickly find a specific link destination and can provide insight into its purpose, the campaign to which it is tied, or anything else that you feel is important.

1. Click **Save**.
