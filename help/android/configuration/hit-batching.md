---
description: Hit batching allows applications to hold hits from being sent until the number of hits in the queue have exceeded the configured limit.
keywords: android;library;mobile;sdk
seo-description: Hit batching allows applications to hold hits from being sent until the number of hits in the queue have exceeded the configured limit.
seo-title: Hit Batching
solution: Experience Cloud,Analytics
title: Hit Batching
topic: Developer and implementation
uuid: ada35be3-242b-4b2b-a828-9bf998dd58b5
---

# Hit batching {#hit-batching}

Hit batching allows applications to hold hits from being sent until the number of hits in the queue have exceeded the configured limit.

>[!IMPORTANT]
>
>To use hit batching, you **must** enable offline tracking and have SDK version 4.1 or later

To enable hit batching, update your `ADBMobileConfig.json` file and specify a value for `batchLimit`:

```js
"analytics": {
    "batchLimit": 5,
    ...
}
```

When the value is set to a number greater than 0, the SDK queues the number of hits equal to the *`batchLimit`* value. After this threshold is passed, all hits in the queue are sent.

The following methods are used with hit batching:

* `Analytics.getQueueSize` returns a `long` with the number of hits currently in the hit batching queue. 

* `Analytics.sendQueuedHits` forces the library to send all hits in the queue no matter how many hits are currently queued. 
* `Analytics.clearQueue` clears all hits from the queue without sending them.
