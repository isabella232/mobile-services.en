---
description: Information to help you implement Lifecycle metrics for Android. Lifecycle metrics are automatically collected for iOS.
keywords: Xamarin
seo-description: Information to help you implement Lifecycle metrics for Android. Lifecycle metrics are automatically collected for iOS.
seo-title: Implement lifecycle
solution: Experience Cloud
title: Implement lifecycle
uuid: 6dccc12e-8b57-4231-9c74-d47bc0ac93ba
---

# Implement lifecycle {#implement-lifecycle}

This information helps you implement Lifecycle metrics for Android. 

>[!TIP]
>
>Lifecycle metrics are automatically collected for iOS.

For the metrics and dimensions that can be measured automatically by the mobile library after lifecycle is implemented, see [Lifecycle Metrics](/help/ios/metrics.md).

## iOS

In iOS, lifecycle metrics are automatically collected.

## Android

In your main activity, set the application context for the Android SDK.

```java
protected override void OnCreate (Bundle bundle) 
{
    ... 
    Config.SetContext (Application.Context); 
    ... 
}
```

In every activity, implement lifecycle calls.

```java
protected override void OnResume()
{
    ...
    Config.CollectLifecycleData (this);
    ...
}
protected override void OnPause() 
{
    ...
    Config.PauseCollectingLifecycleData ();
    ...
}
```