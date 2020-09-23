---
description: Android widgets can be tracked by using the same methods as your app. Widgets share the application context with your app, so hit order and visitor identification is preserved.
keywords: android;library;mobile;sdk
seo-description: Android widgets can be tracked by using the same methods as your app. Widgets share the application context with your app, so hit order and visitor identification is preserved.
seo-title: Android widgets
solution: Experience Cloud,Analytics
title: Android widgets
topic: Developer and implementation
uuid: 1a3718ff-967b-4c8e-ae0b-ba15bddbda0a
---

# Android widgets {#android-widgets}

Android widgets can be tracked by using the same methods as your app. Widgets share the application context with your app, so hit order and visitor identification is preserved.

The following guidelines will help you track Android widgets:

* Do not implement lifecycle metrics ( `startActivity`/ `stopActivity`) calls in the widget. 

* To track when a widget is added to the home screen, add a `trackState` or `trackEvent` call to the `onEnabled` method of the widget. 

* To track when the app is launched from a widget, add a `trackState` or `trackEvent` call before you create the intent to launch your application. 

* To track the context of an action, you can define a `ContextData` variable that provides the option to segment each action separately (for example, `AppExperienceType="widget"` vs. `app`).

