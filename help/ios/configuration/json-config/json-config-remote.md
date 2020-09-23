---
description: You can load a different ADBMobile JSON Config file when the application starts.
seo-description: You can load a different ADBMobile JSON Config file when the application starts.
seo-title: Override the ADBMobile JSON config path
solution: Experience Cloud,Analytics
title: Override the ADBMobile JSON config path
topic: Developer and implementation
uuid: 0d1be674-c634-4a48-aa31-5701681911b9
---

# Override the ADBMobile JSON config path {#override-the-adbmobile-json-config-path}

You can load a different ADBMobile JSON Config file when the application starts.

The `ADBMobile overrideConfigPath:filePath` method allows you to specify the path to a different `ADBMobile.json` configuration file when the application starts. This method must be called in the `applicationDidFinishLaunchingWithOptions` method, and the call must occur before any other Experience Cloud SDK call, such as `collectLifecycleData`.

When you call this method with a different path, a one-time override of the configuration file occurs until the application is closed.

For example:

```objective-c
NSString *filePath = [[NSBundle mainBundle] pathForResource:@"ExampleJSONFile" ofType:@"json"]; 
[ADBMobile overrideConfigPath:filePath];
```

