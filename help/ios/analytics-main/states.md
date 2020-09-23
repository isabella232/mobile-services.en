---
description: States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a track state call should be sent. In iOS, a state is typically tracked in the viewDidLoad method of each view.
seo-description: States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a track state call should be sent. In iOS, a state is typically tracked in the viewDidLoad method of each view.
seo-title: Track App States
solution: Experience Cloud,Analytics
title: Track App States
topic: Developer and implementation
uuid: 12cca4eb-1f15-4cec-a58f-76b69eaff99d
---

# Track app states {#track-app-states}

States are the different screens or views in your application. Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a track state call should be sent. In iOS, a state is typically tracked in the viewDidLoad method of each view.

>[!TIP]
>
>To track states, make a call to `trackState`. States are not automatically tracked.

## Tracking states {#section_380DF56C4EE4432A823940E4AE4C9E91}

1. Add the library to your project and implement lifecycle.

    For more information, see *Add the SDK and Config File to your Project* in [Core Implementation and Lifecycle](/help/ios/getting-started/dev-qs.md). 
1. Import the library.

   ```objective-c
   #import "ADBMobile.h"
   ```

1. Call `trackState` to send a hit for this state view.

   ```objective-c
   [ADBMobile trackState:@"Login Screen"  
                    data:nil];
   ```

In Adobe Mobile services, the **[!UICONTROL State Name]** is reported in the *`View State`* variable, and a view is recorded for each `trackState` call. In other Analytics interfaces, **[!UICONTROL View State]** is reported as **[!UICONTROL Page Name]**, and state views is reported as page views.

## Sending additional data {#section_CFDB4F944496401786A145C209AB387C}

In addition to the **[!UICONTROL State Name]**, you can send additional context data with each track action call:

```objective-c
NSMutableDictionary *contextData = [NSMutableDictionary dictionary]; 
[contextData setObject:@"logged in" forKey:@"myapp.login.LoginStatus"]; 
[ADBMobile trackState:@"Home Screen" data:contextData];
```

Context data values must be mapped to custom variables: 

![](assets/map-variable-context-state.png)

## App state reporting {#section_0F6A54AB7A3F42C9BB042D86A0FC4630}

States are typically viewed by using a pathing report so you can see how users navigate your app and which states are viewed most.

| | |
|--- |--- |
|Adobe Mobile Services | The **[!UICONTROL View States]** report. This report is based on the paths that the users took through your application. A sample path is  **[!UICONTROL Home]**  >  **[!UICONTROL Settings]**  > **[!UICONTROL Feed]**. |
|Adobe Analytics|States can be viewed anywhere that Pages can be viewed, such as the **[!UICONTROL Pages]** report, the **[!UICONTROL Page Views]** report, and the **[!UICONTROL Path]** report. |
|Ad hoc analytics|States can be viewed anywhere Pages can be viewed by using the **[!UICONTROL Page]** dimension, **[!UICONTROL Page Views]** metric, **[!UICONTROL Path]** reports. |
