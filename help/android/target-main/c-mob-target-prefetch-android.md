---
description: The Adobe Target prefetch feature uses the Android Mobile SDKs to fetch offer content as few times as possible by caching the server responses.
seo-description: The Adobe Target prefetch feature uses the Android Mobile SDKs to fetch offer content as few times as possible by caching the server responses.
seo-title: Prefetch offer content in Android
title: Prefetch offer content in Android
uuid: 063451b8-e191-4d58-8ed8-1723e310ad1a
index: y
internal: n
snippet: y
---

# Prefetch offer content in Android{#prefetch-offer-content-in-android}

The Adobe Target prefetch feature uses the Android Mobile SDKs to fetch offer content as few times as possible by caching the server responses.

This process reduces the load time, prevents multiple network calls, and allows Adobe Target to be notified which mbox was visited by the mobile app user. All content will be retrieved and cached during the prefetch call, and this content will be retrieved from the cache for all future calls that contain cached content for the specified mbox name.

Prefetch content does not persist across launches. The prefetch content is cached as long as the application lives or until the `clearPrefetchCache()` method is called.

>[!IMPORTANT]
>
>Target prefetch APIs have been available since SDK version 4.14.0. For more information about parameter limitations, see [https://developers.adobetarget.com/api/#batch-input-parameters](https://developers.adobetarget.com/api/#batch-input-parameters).

In SDK version 4.14 or later, if specified, the `environmentId` is picked from the ADBMobileConfig.json file when initiating a v2 batch mbox TnT call. If no `environmentId` is specified in this file, no environment parameter is sent in TNT batch mbox call, and offer is delivered for the default environment.

For example: 

```java
if (MobileConfig.getInstance().mobileUsingTarget()){ 
            long environmentID = MobileConfig.getInstance().getEnvironmentID(); 
            if(environmentID != 0L){ 
                parametersJson.put(TargetJson.ENVIRONMENT_ID, environmentID); 
            } 
        }
```

## Pre-fetch Methods {#section_05967F1F3A554B0FBC2C08A954554BDE}

Here are the methods that you can use for prefetch in Android:

### prefetchContent

Sends a prefetch request with an array of locations to the configured Target server and returns the request status in the provided callback.

**Syntax**

```
public static void prefetchContent(
final List<TargetPrefetchObject> targetPrefetchArray,
final Map<String, Object> profileParameters,
final TargetCallback<Boolean> callback)
```

**Parameters**

|Name |Description |
|--- |--- |
|targetPrefetchArray|Array of `TargetPrefetchObjects` that contains the name and mboxParameters for each Target location to prefetch.|
|profileParameters|Contains the keys and values of profile parameters to be used with every location prefetch in this request.|
|callback|Invoked when the prefetch is complete. Returns `true` if the prefetch was successful and `false` if the prefetch was unsuccesful.|

### loadRequests

Executes a batch request for multiple mbox locations that are specified in the requests array. &nbsp;Each object in the array contains a callback function, which will be invoked when content is available for its given mbox location.

>[!IMPORTANT]
>
>If the content for the requested locations is already cached, it will be returned immediately in the provided callback. Otherwise, the SDK will send a network request to the Target servers to retrieve the content.

**Syntax:**

```
public static void loadRequests( final List<TargetRequestObject> requestArray,  final Map<String, Object> profileParameters)
```

**Parameters**

|Name |Description |
|--- |--- |
|requestArray|Array of `TargetRequestObjects` that contains the name, default content, parameters, and callback function per location to retrieve.|
|profileParameters|Contains keys and values of profile parameters to be used with every location prefetch in this request.|

### clearPrefetchCache

Clears the data that was cached by Target Prefetch.

**Syntax**:

`public static void clearPrefetchCache();`

**Parameters**: N/A

### createTargetRequestObject

Creates and returns an instance of `TargetRequestObject` with the provided data.

**Syntax**

```
public static TargetPrefetchObject createTargetRequestObject( 
final String mboxName,
final String defaultContent, 
final Map<String, Object> mboxParams, 
final Map<String, Object> orderParams, 
final Map<String, Object> productParams, 
final Target.TargetCallback<String> callback)
```

### createTargetPrefetchObject

Creates and returns an instance of TargetPrefetchObject with the provided data.

**Syntax**:

```
public static TargetPrefetchObject createTargetPrefetchObject( 
final String mboxName, 
final Map<String, Object> mboxParams) 
final Map<String, Object> orderParams, 
final Map<String, Object> productParams)
```

## Public Classes {#section_A273E53F069E4327BBC8CE4910B37888}

Here are the public classes that support pre-fetch in Android:

**Class Reference: TargetPrefetchObject**

Encapsulates the mbox name and the parameters that are used for mbox prefetch.

| Property | Description |
|--- |--- |
|name|Type: String<br>Name of the location that will be prefetched.|
|mboxParameters|Type: Map`<String, Object>` <br>Collection of key-value pairs that will be attached as `mboxParameters` for this  `TargetPrefetchObject`'s request.|
|orderParameters|Type: Map `<String, Object>` <br>Collection of key-value pairs that will be attached to current mbox under the order node.|
|productParameters|Type: Map `<String, Object>` <br>Collection of key-value pairs that will be attached to current mbox under the product node.|

**Class Reference: TargetRequestObject**

This class encapsulates the mbox name, default content, mbox parameters and the return callback used for Target location requests.

| Property | Description |
|--- |--- |
|mboxName|Type: String <br>Name of the requested location.|
|mboxParameters|Type: Map `<String, Object>` <br>Collection of key-value pairs that will be attached as `mboxParameters` for this  `TargetRequestObject`.|
|orderParameters|Type: Map `<String, Object>` <br>Collection of key-value pairs that will be attached to current mbox under the order node.|
|productParameters|Type: Map `<String, Object>` <br>Collection of key-value pairs that will be attached to current mbox under the product node.|
|defaultContent|Type: String <br>String value that is returned in the callback if the SDK is unable to retrieve content from Target servers.|
|callback|Type: Target.TargetCallback`<String>` <br>Function pointer that will be called when content for the given `TargetRequestObject` is available.|

## Code Sample {#section_BF7F49763D254371B4656E17953D520C}

Here is an example of how to prefetch content by using the Android SDKs:

```java
// When your app launches, prefetch the content for a list of locations. 
// Define the list of mboxes that you want to prefetch. 
List<TargetPrefetchObject> prefetchMboxesList = new ArrayList<>(); 
  
Map<String, Object> mboxParameters1 = new HashMap<>(); 
mboxParameters1.put("status", "platinum"); 
prefetchMboxesList.add(Target.createTargetPrefetchObject("mboxName1", mboxParameters1));

Map<String, Object> mboxParameters2 = new HashMap<>(); 
mboxParameters2.put("userType", "paid"); 
 
List<String> purchasedIds = new ArrayList<String>(); 
purchasedIds.add("34"); 
purchasedIds.add("125");  
Map<String, Object> orderParameters2 = new HashMap<>(); 
orderParameters2.put("id", "ADCKKIM"); 
orderParameters2.put("total", "344.30"); 
orderParameters2.put("purchasedProductIds",  purchasedIds); 
  
Map<String, Object> productParameters2 = new HashMap<>(); 
productParameters2.put("id", "24D3412"); 
productParameters2.put("categoryId","Books"); 
  
prefetchMboxesList.add(Target.createTargetPrefetchObject("mboxName2", mboxParameters2, orderParameters2, productParameters2));

// Define the profile parameters map. 
Map<String, Object> profileParameters = new HashMap<>(); 
profileParameters.put("ageGroup", "20-32");

// Define the target callback for the prefetch call status. 
Target.TargetCallback<Boolean> prefetchStatusCallback = new Target.TargetCallback<Boolean>() { 
    @Override 
    public void call(final Boolean status) { 
        // check the returned status for the prefetch call 
    }};

// Call the prefetchContent API. 
Target.prefetchContent(prefetchMboxesList, profileParameters, prefetchStatusCallback);

// When the content is required, you can initiate the locations request. 
// Define the list of target request objects. 
List<TargetRequestObject> locationRequests = new ArrayList<>(); 
  
Target.TargetCallback<String> callback1 = new Target.TargetCallback<String>() { 
    @Override 
    public void call(final String content) { 
        // check the returned content for mboxName1. 
    }}; 
  
locationRequests.add(Target.createTargetRequestObject("mboxName1", "defaultContent1", mboxParameters1, callback1));

Target.TargetCallback<String> callback2 = new Target.TargetCallback<String>() { 
    @Override 
    public void call(final String content) { 
        // check the returned content for mboxName2. 
    }}; 
  
locationRequests.add(Target.createTargetRequestObject("mboxName2", "defaultContent2", mboxParameters2, orderParameters2, productParameters2, callback2)); 
  
// Call the loadRequests API. 
Target.loadRequests(locationRequests, profileParameters); 
```

## Additional Information {#section_A454BAD1CD49423E86C71BAEE06125FD}

Here is some additional information about these samples:

* `ProductParameters` only allows the following keys:

    * `id` 
    * `categoryId`

* `OrderParameters` only allows the following keys:

    * `id` 
    * `total` 
    * `purchasedProductIds`

* `purchasedProducts` accepts an ArrayList of strings.