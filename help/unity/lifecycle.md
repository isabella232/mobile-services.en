---
description: null
keywords: Unity
seo-description: null
seo-title: Implement Lifecycle
solution: Experience Cloud
title: Implement Lifecycle
uuid: 7ff2c194-569c-42a6-922d-dccd2aa9eb8d
---

# Implement Lifecycle{#implement-lifecycle}

For more information about the metrics and dimensions that can be measured automatically by the mobile library after lifecycle is implemented, see [Lifecycle Metrics in Android](/help/android/metrics.md) or [Lifecycle in iOS](/help/ios/metrics.md).

## iOS

Lifecycle metrics are automatically collected in iOS.

## Android

In your Unity script, you set the application context for the Android SDK. Add the following code to the `Awake()` function of your FIRST scene:

```java
void Awake()
 {
  ...
  ADBMobile.SetContext();
  ...
 }
```

To collect lifecycle metrics, add the following code to all of your scene scripts:

```java
void OnEnable()
 {
  ...
  ADBMobile.CollectLifecycleData (); 
  ...
 }
 
 void OnDisable()
 {
  ...
  ADBMobile.PauseCollectingLifecycleData (); 
  ...
 }
  
 void OnApplicationPause(bool isPaused) 
 {
  ...
  if (isPaused) {
   ADBMobile.PauseCollectingLifecycleData (); 
  }  
  else {
   ADBMobile.CollectLifecycleData(); 
  }
  ...
 }

```

