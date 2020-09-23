---
description: States are the different screens or views in your application.
seo-description: States are the different screens or views in your application.
seo-title: Track App States
solution: Experience Cloud,Analytics
title: Track App States
topic: Developer and implementation
uuid: 69c99d05-5816-4c86-97c5-d218dc26c129
---

# Track app states {#track-app-states}

States are the different screens or views in your application.

Each time a new state is displayed in your application, for example, when a user navigates from the home page to the news feed, a `trackState` call is sent. In Android, `trackState` is typically called each time a new activity is loaded.

## Tracking states {#section_380DF56C4EE4432A823940E4AE4C9E91}

1. Add the library to your project and implement lifecycle.

   For more information, see *Add the SDK and Config File to your IntelliJ IDEA or Eclipse Project* in [Core implementation and lifecycle](/help/android/getting-started/dev-qs.md).
 
1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. In the `onCreate` function, call `trackState` to send a hit for this state view: 

   ```java
   @Override 
   public void onCreate(Bundle savedInstanceState) { 
       super.onCreate(savedInstanceState); 
       setContentView(R.layout.main); 

       // Adobe - track when this state loads 
       Analytics.trackState("State Name", null); 
   }
   ```

The `"State Name"` is reported in the `View State` variable in Adobe Mobile services, and a view is recorded for each `trackState` call. In other Analytics interfaces, `View State` is reported as `Page Name`, and `state views` is reported as `page views`.

## Send additional data {#section_CFDB4F944496401786A145C209AB387C}

In addition to the `"State Name"`, you can send additional context data with each track action call:

```java
@Override 
public void onCreate(Bundle savedInstanceState) { 
    super.onCreate(savedInstanceState); 
    setContentView(R.layout.main); 
  
    // Adobe - track when this state loads 
    HashMap<String, Object> exampleContextData = new HashMap<String, Object>(); 
    exampleContextData.put("myapp.login.LoginStatus", "logged in"); 
    Analytics.trackState("Home Screen", exampleContextData); 
}
```

Context data values must be mapped to custom variables in Adobe Mobile services: 

![](assets/map-variable-context-state.png)

## App state reporting {#section_0F6A54AB7A3F42C9BB042D86A0FC4630}

States are typically viewed by using a pathing report, which allows you to see how users navigate your app and which states are most frequently viewed.

| | |
|--- |--- |
|Adobe Mobile Services | The **[!UICONTROL View States]** report. This report is based on the paths that the users took through your application. A sample path is  **[!UICONTROL Home]**  >  **[!UICONTROL Settings]**  > **[!UICONTROL Feed]**. |
|Adobe Analytics|States can be viewed anywhere that Pages can be viewed, such as the **[!UICONTROL Pages]** report, the **[!UICONTROL Page Views]** report, and the **[!UICONTROL Path]** report. |
|Ad hoc analytics|States can be viewed anywhere Pages can be viewed by using the **[!UICONTROL Page]** dimension, **[!UICONTROL Page Views]** metric, **[!UICONTROL Path]** reports. |


