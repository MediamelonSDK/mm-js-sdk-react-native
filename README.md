
# 📦 MediaMelon React Native Video SDK Integration Guide

This SDK is designed to integrate with [`react-native-video@5.2.1`](https://www.npmjs.com/package/react-native-video/v/5.2.1) and provides support for advanced playback analytics via MediaMelon.

---

## 🚀 Step 1: Import the SDK Package

In your React Native app entry point (e.g., `App.js`):

### Using NPM Package

```js
import {MMReactNativeVideoSDK} from 'mediamelon-js-react-native-sdk';
```

### Using Local Minified JS File

```js
import {MMReactNativeVideoSDK} from './mmsmartstreaming_reactnative.min.js';
```

---

## ⚙️ Step 2: Register and Initialize the SDK

Wrap your `Video` component using the SDK wrapper.

```js
const MMPlayer = MMReactNativeVideoSDK(Video);
```

Use the wrapped `MMPlayer` component in your app:

```jsx
<MMPlayer
  source={{ uri: 'STREAM_URL' }}
  mmOptions={{
    register: {
      customerId: 'CUSTOMER_ID',
      subscriberId: 'SUBSCRIBER_ID',
      subscriberType: 'SUBSCRIBER_TYPE',
      subscriberTag: 'SUBSCRIBER_TAG',
      hashSubscriberId: false,
      playerName: 'PLAYER_NAME',
      playerBrand: 'PLAYER_BRAND',
      playerModel: 'PLAYER_MODEL',
      playerVersion: 'PLAYER_VERSION',
      basePlayerName: 'BASE_PLAYER_NAME',
      basePlayerVersion: 'BASE_PLAYER_VERSION',
      domainName: 'DOMAIN_NAME',
      applicationName: 'APP_NAME',
      applicationVersion: 'APP_VERSION',
      deviceMarketingName: 'DEVICE_MARKETING_NAME'
    },
    contentMetadata: {
      assetName: 'ASSET_NAME',
      assetId: 'ASSET_ID',
      videoId: 'VIDEO_ID',
      contentType: 'CONTENT_TYPE',
      genre: 'GENRE',
      drmProtection: 'DRM_PROTECTION',
      episodeNumber: 'EPISODE_NUMBER',
      season: 'SEASON',
      seriesTitle: 'SERIES_TITLE',
      isLive: false
    },
    customTags: {
      "KEY1": "VALUE_STRING1",
      "KEY2": "VALUE_STRING2"
    },
    experimentName: "EXPERIMENT_NAME",
    subPropertyId: "SUB_PROPERTY_ID",
    viewSessionId: "VIEW_SESSION_ID"
  }}
/>
```

> **Note:** `CUSTOMER_ID` is provided by MediaMelon. If you don't have one, contact [customer-support@mediamelon.com](mailto:customer-support@mediamelon.com).

---

## ⚠️ Step 3: Known Limitations

- **Buffering events are not supported on Apple platforms.**
- **onBuffer() is not triggered consistently on Android.**
- **Seek start and complete events are internally tracked due to inconsistency with `onSeek()` listener.**

---
