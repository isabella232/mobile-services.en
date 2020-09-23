---
description: null
seo-description: null
seo-title: Developer quick start
solution: Experience Cloud,Analytics
title: Developer quick start
topic: Developer and implementation
uuid: 11c06fcf-d5e4-4858-9a4e-3bf66cdd2a48
---

# Developer quick start{#developer-quick-start}

Here is some information about how to implement the Universal Windows Platform library.

>[!IMPORTANT]
>
>To implement the SDK, you need Visual Studio 2013 or later.

## Get the SDK {#section_99FE1A17A36D4A2C943939023CF6265C}

After you unzip the [SDK download](https://github.com/Adobe-Marketing-Cloud/mobile-services/releases) file, you will have a separate folder for each supported architecture and platform combination. You will also have an `ADBMobileConfig.json` file. For more information about this file, see [ADBMobileConfig.json config file](/help/universal-windows/c-configuration/c.json.md).

## Select the correct version {#section_E53C5AA7D5474824A89BB32C003865A1}

Different `.dll/.winmd` files are provided for each supported architecture (x86, x64, ARM).

>[!IMPORTANT]
>
>The version of `ADBMobile.winmd` does not reflect the version of the library. The `.winmd` file contains only metadata and has a version number of `255.255.255.255`, which is accepted behavior according to Microsoft. For more information, see [How do I add assembly information for a WinRT C++ / CX component dll?](https://social.msdn.microsoft.com/Forums/windowsapps/en-US/6bcccaee-aa53-4770-bd5b-1205977f1ca7/how-do-i-add-assembly-information-for-a-winrt-c-cx-component-dll?forum=winappswithnativecode). To check the version of the library you are using, check the version of the underlying `ADBMobile.dll` file.

## Syntax Differences {#section_A02DE120B6D240F5AFFE7509755C4F14}

The Universal Windows Platform library can be used in several programming languages. The examples in this guide are in WinJS (JavaScript), if you are using a different language, might need to be modified. When you consume winmd methods from winJS, all methods automatically have their first letter lowercased.

The main difference between the implementations is the data structure used for context data. Additionally, when using the SDK in a WinJS project, use an empty string ( `""` or `''`) instead of `null` for empty string values.

## Add the library and config File to your project - C# {#section_93C25D893B4A4CD3B996CF3C5590C8DC}

1. Launch Visual Studio and open your solution. 
1. In the **[!UICONTROL Solution Explorer]**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference]**. 

1. Select the correct version  of the library and browse to the associated ADBMobile.winmd file.

    For more information, see *Select the correct version* section on this page.

1. Click **Add**. 

1. Verify that the ADBMobile.winmd file is checked in the **[!UICONTROL Reference Manager]** window and click **[!UICONTROL OK]**. 

1. In the **[!UICONTROL Solution Explorer]**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference]**. 

    If you also have a C++ project in your solution, skip this step.

1. In the **[!UICONTROL Windows]** tab on the left, select **[!UICONTROL Extensions]**, select and add **[!UICONTROL Visual C++ 2015 Runtime for Universal Windows Platform Apps]**. 

1. Add the following line to your class: 

   ```csharp
   using ADBMobile;
   ```

1. Right-click your project and click **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to the `ADBMobileConfig.json` file and click **[!UICONTROL Add]**. 

1. Right-click on the `ADBMobileConfig.json` file in your solution and select **[!UICONTROL Properties]**. 

1. Change **[!UICONTROL Build Action]** to **[!UICONTROL Content]**.

## Add the library and config file to your project - C++ {#section_A95C1D18F6144F37ADC8F51590F3983E}

1. Launch Visual Studio and open your solution. 
1. In the **[!UICONTROL Solution Explorer]**, right-click your project and select **[!UICONTROL Add]** > **[!UICONTROL References]**. 

1. Select the correct version  of the library and add a reference to the associated ADBMobile.winmd file.

    For more information, see *Select the correct version* section on this page. 

1. Click **[!UICONTROL Add]**. 

1. Verify that `ADBMobile.winmd` is checked in the **[!UICONTROL Reference Manager]** window and click **[!UICONTROL OK]**. 

1. Add the following line to your class: 

   ```c++
   using namespace ADBMobile;
   ```

1. Right-click your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to `ADBMobileConfig.json` file and click **[!UICONTROL Add]**. 

1. Right-click the `ADBMobileConfig.json` file in your solution and select **[!UICONTROL Properties]**. 

1. On the **[!UICONTROL General]** tab, change **[!UICONTROL Content]** to **[!UICONTROL Yes]** and click **[!UICONTROL OK]**.

## Add the library and config file to your project - WinJS {#section_FF83113EBF4742AFA929F4AC28F92DB5}

1. Launch Visual Studio and open your solution. 

1. In the **[!UICONTROL Solution Explorer]**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference]**. 

1. Select the correct version of the library and browse to the associated ADBMobile.winmd file. 

1. Click **[!UICONTROL Add]**. 

1. Verify that the ADBMobile.winmd file is checked in the **[!UICONTROL Reference Manager]** window and click **[!UICONTROL OK]**. 

1. In the **[!UICONTROL Solution Explorer]**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference]**. 

    If you also have a C++ project in your solution, skip this step.

1. In the **[!UICONTROL Windows]** tab on the left, select **[!UICONTROL Extensions]** and select and add **[!UICONTROL Visual C++ 2015 Runtime for Universal Windows Platform Apps]**. 

1. Right-click your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to the `ADBMobileConfig.json` file and click **[!UICONTROL Add]**. 

1. Right-click the `ADBMobileConfig.json` file in your solution and select **[!UICONTROL Properties]**. 

1. With **[!UICONTROL File Properties]** selected, ensure **[!UICONTROL Package Action]** is set to **[!UICONTROL Content]**.

    For JavaScript projects, the file is set to Content by default.

## Update The ADBMobileConfig.json config file {#section_0BC8CC0E4AAD4AC385FA0AEDC3C56AFE}

The `ADBMobileConfig.json` file contains global SDK settings and is located at your project root after you complete the steps in the *Add the library and config file to your project* section. If your `ADBMobileConfig.json` file was not pre-configured by Adobe Mobile Services, you need to update a few values to get started.

Here is an example of an `ADBMobileConfig.json` file:

```js
{ 
    "version" : "1.0", 
    "analytics" : { 
        "rsids" : "coolApp", 
        "server" : "my.CoolApp.com", 
        "charset" : "UTF-8", 
        "ssl" : true, 
        "offlineEnabled" : true, 
        "lifecycleTimeout" : 300, 
        "privacyDefault" : "optedin", 
        "poi" : [ 
                    ["san francisco",37.757144,-122.44812,7000], 
                    ["santa cruz",36.972935,-122.01725,600] 
                ] 
    }, 
 "target" : { 
  "clientCode" : "myTargetClientCode", 
  "timeout" : 1 
 }, 
 "audienceManager" : { 
  "server" : "myServer.demdex.com" 
 } 
}
```

At a minimum, update the following values for the solutions you are using:

* **Adobe Analytics**: `rsids` and `server` 

* **Adobe Target**: `clientCode` 

* **Adobe Audience Manager**: `server`

For more information, see [SDK methods](/help/universal-windows/c-configuration/methods.md).

## Debugging {#section_3A10376A60394A15BEE483323E0CD4AA}

To enable debugging for the SDK, call `ADBMobile.Config.setDebugLogging(true);`.

For C Sharp and JavaScript apps, you need to enable native code debugging by completing the following steps (native code debugging is the default setting for C++ apps):

### C Sharp

1. Right-click the project, click  **[!UICONTROL Properties]** > **[!UICONTROL Debug tab]**. 

1. Change the debugger type drop down to **Native Only**.

### JavaScript

1. Right-click the project, click **[!UICONTROL Properties]** > **[!UICONTROL Configuration Properties]** > **[!UICONTROL Debug tab]**. 

1. Change the debugger type drop down to **[!UICONTROL Native Only]**.

That's it! You're now ready to implement Analytics, Target, and Audience Management in your Universal Windows Platform app.

