---
title: SDK Comparison
---

There are two ways to integrate the bot in Android/iOS:
* **Native SDK** is installed right inside your app.
* Your Android app opens up Haptik's **Web SDK** only as a _webview_.

### Limitations of Native SDK
* Native SDK has not been redesigned and is older
* Language support missing
* Native SDKs do not have out-of-the-box language support that the Web SDK does
* Bot prompts are not available
* Not very customisable except for primary color.
* CSS injections not supported. 
* You can build, bend and mould our Web SDK using CSS.
* The SDK size increases: Android by 1 MB and iOS by ~3.4 MB

### Why use Native SDKs?
* Native apps are always superior when it comes to overall performance -
  * They will always load faster.
  * The animations run smoother.

### Notes
* Don’t replicate app features within the bot, use deep link instead.
* Haptik allows full CSS customisation to completely change the look only with Web SDK.
