---
title: Migration
---

<AUTOGENERATED_TABLE_OF_CONTENTS>

<a name="moving-from-210---220"></a>

## Moving from 2.1.0 → 2.2.0
**HaptikLib.init()** has been changed to take an Application reference in the argument
**HaptikLib.setDeviceToken(String)** now required a Context in the argument as well
**HaptikLib.setActivityLifecycleCallback(Application)** has been removed  
**ErrorType** ERROR_LIFECYCLE_CALLBACKS_NOT_SET has been removed from HaptikException


<a name="moving-from-220---230"></a>

## Moving from 2.2.0 → 2.3.0
Update following dependencies in your app’s build.gradle,
```java
compile 'in.til.sdk.android:sdk-core:1.3.1'
compile 'in.til.sdk.android.data:dmp-pc:1.2.3'
```

Add following dependencies in your app’s build.gradle,
```java
compile 'com.uber.sdk:rides-android:0.6.1'
compile 'com.android.support.constraint:constraint-layout:1.0.2'
```
<a name="moving-from-230---240"></a>

## Moving from 2.3.0 → 2.4.0
AmazonPay support has been added in our SDK. Make sure you have to latest AAR file for that SDK, and include in your app same way you include the Haptik SDK AAR

PERMISSION:
```xml
<uses-permission android:name="android.permission.READ_PHONE_STATE" />
```
It’s being used for our referral system. You may force remove it if you’re not using our referral system


<a name="moving-from-240---250"></a>

## Moving from 2.4.0 → 2.5.0
MessagingActivity has been renamed to ChatActivity. Please make that change, otherwise things would break.



<a name="moving-from-250---260"></a>

## Moving from 2.5.0 → 2.6.0
PERMISSION:
```xml
<uses-permission android:name="android.permission.VIBRATE" />
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />
```
Both of these permissions are not mandatory as of now. You can force remove them if you don’t already ask for them

<a name="moving-from-260---290"></a>

## Moving from 2.6.0 → 2.9.0
Update following dependencies in your app’s build.gradle,
```java
compile 'org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.0'
```

PhonePe support has been added in our SDK. Make sure you follow the steps mentioned below for it to work properly.

Add following dependencies in your root build.gradle’s repositories block,
```java
maven {
   url "http://phonepe.bintray.com/PhonePeThinAndroidSDK"
   credentials {
       username 'Ask Haptik'
       password 'Ask Haptik'
   }
}
```

Add following dependencies in your app’s build.gradle,

```java
compile 'phonepe.thinsdk.android.release:merchantsdk:0.3.2'
```

For security purpose, PhonePe requires the SHA-1(which you will need to provide us) of your app’s production and debug keystore(if both are different) to generate the PhonePe-ID for your app.
Once we get the SHA-1, PhonePe-ID is generated from it and you’ll need to add it as <meta-data> info in AndroidManifest.xml inside <application> tag.

```xml
<meta-data
android:name="com.phonepe.android.sdk.AppId"
android:value="PhonePe-ID" />
```

<a name="moving-from-290---2100"></a>

## Moving from 2.9.0 → 2.10.0
- Haptik SDK is now distributed as a gradle dependency! So make sure you add our private maven repo in your app’s root build.gradle.

```css
maven {
   url "http://artifactory.hellohaptik.com:8081/artifactory/libs-release-local"
   credentials {
       username "{ASK HAPTIK FOR USERNAME}"
       password "{ASK HAPTIK FOR PASSWORD}"
   }
}
```
- After this add Haptik’s dependency as below,

Haptik SDK without cab functionality
```java
compile 'ai.haptik.android.sdk:haptiklib-core:2.10.0-30146'
```

Haptik SDK with cab functionality
```java
compile 'ai.haptik.android.sdk:haptiklib-cab:2.10.0-30146'
```

- You may remove all haptik related maven based dependencies except AmazonPay since it’s standalone AAR based

- If you're using our `cab` functionality/sdk then you would now need to enable it programmatically. Make sure to add this line just anytime before or just after you call HaptikLib.init()

```java
HaptikLib.setApis(CabApiFactory.getCabApi());
```

<a name="moving-from-2100---300"></a>
## Moving from 2.10.0 → 3.0.0
- This release adds more modularity to Haptik SDK by introducing payments as separate module. From now onwards, payments is not a part of `core` module.

- Add the following dependency for using payment module,

Haptik SDK with payment functionality
```java
compile 'ai.haptik.android.sdk:haptiklib-payment:3.0.0-30150'
```

- Please DO NOT remove AmazonPay dependency as it's standalone AAR, and not a maven dependency, if you are using payment.

- init function of HaptikLib has got signature changes, so it will break dependent app compilation. New InitData has been introduced along with a Builder. Please check the below example:

```java
InitData initData = new InitData.Builder(this)
   .baseUrl(URL)
   .clientMainActivityClass(YourMainActivity.class)
   .apiOptions(CabApiFactory.getCabApi())// For Cabs
   .apiOptions(PaymentApiFactory.getPaymentApi())// For payments
   .debugEnabled(true)// or false, based on build variant
   .notificationSound(R.raw.notification_sound)
   .build();

HaptikLib.init(initData);

```

<a name="moving-from-300---310"></a>
## Moving from 3.0.0 → 3.1.0
- After this update Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.1.0-31158'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.1.0-31158'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.1.0-31158'
```

- Signature change of `logout` method. 
It now takes a Callback object and provides callback whether logout was success or not

- If you're using Haptik's payment SDK then please note that `AmazonPay` dependency has been updated. Please make you get a new AAR along with this version.

<a name="moving-from-310---320"></a>
## Moving from 3.1.0 → 3.2.0
- This update is primarily a bug fix update.

<a name="moving-from-320---330"></a>
## Moving from 3.2.0 → 3.3.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.3.0-33164'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.3.0-33164'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.3.0-33164'
```

- Update your targetSdkVersion to API 26.
- Update your Gradle to 3.0.0.
- Update your play services to 11.0.4.
- `Router.addMoneyToWallet()` is deprecated now. Please use `Router.showWallet()` for opening wallet balance screen.

<a name="moving-from-330---340"></a>
## Moving from 3.3.0 → 3.4.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.4.0-34168'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.4.0-34168'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.4.0-34168'
```
- `HaptikLib#setDeviceToken()` is now deprecated. Use either `setGcmDeviceToken()` or `setFcmDeviceToken()` depending on your usage
- `Name` is not a mandatory field anymore for `SignUpData` creation with any **AuthType**
- `City` is not a mandatory field anymore for `SignUpData` creation with any **AuthType**
- The `SignUpData` class has less restrictions for parameters, to smooth out the client sign up in Haptik SDK. For more details related to parameters changed for individual Authentication Type, please refer [User Authentication](#user-authentication).
- A new `HaptikSignupProgessView` has been added, which can be used to display while the user is being signed up in Haptik SDK. For more details related to its implementation, please refer Javadoc and section [Integrate Haptik Signup Progress View](#integrating-the-progress-view).

<a name="moving-from-340---350"></a>
## Moving from 3.4.0 → 3.5.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.5.0-35173'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.5.0-35173'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.5.0-35173'
```

- From now `NullPointerException` will be thrown if `clientMainActivityClass` field is not set in `InitData`.

<a name="moving-from-350---360"></a>
## Moving from 3.5.0 → 3.6.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.6.0-36175'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.6.0-36175'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.6.0-36175'
```

- Since SSO SDK is integrated, you'll need to add the below information for it to work:

```
<!-- Please don't use string resources here as it will not work  -->
<provider android:name="com.login.nativesso.provider.TgidSaver"
    android:authorities="androidcontentprovidersso.tg.UNIQUE_CUSTOM_SUFFIX"
    android:exported="true" />
```

Here are the details for updating the above information and creating the `UNIQUE_CUSTOM_SUFFIX`:
- `androidcontentprovidersso.tg` is constant prefix.
- After the prefix, give a specific name identifier for your app.
- `UNIQUE_CUSTOM_SUFFIX` should be **unique** otherwise app will not install on the device due to common authority name.
- For example, if your package name is com.abc.xyz, use COM_ABC_XYZ as `UNIQUE_CUSTOM_SUFFIX`.

This way `android:authorities` will look like:

```
androidcontentprovidersso.tg.COM_ABC_XYZ
```

 Once the provider configuration is set, you'll need to add a meta-data for the same:

```
<!-- For SSO initialization -->
<meta-data android:name="ai.haptik.android.sdk.SsoProviderAuthority"
   android:value="androidcontentprovidersso.tg.UNIQUE_CUSTOM_SUFFIX" />
```

<a name="moving-from-360---370"></a>
## Moving from 3.6.0 → 3.7.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.7.0-37176'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.7.0-37176'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.7.0-37176'
```

- Added a public method `HaptikLib.updateUserToken()` for client to update user token.

<a name="moving-from-370---381"></a>
## Moving from 3.7.0 → 3.8.1
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.8.1-38277'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.8.1-38277'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.8.1-38277'
```

<a name="moving-from-381---390"></a>
## Moving from 3.8.1 → 3.9.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:3.9.0-39178'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:3.9.0-39178'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:3.9.0-39178'
```

- Truecaller is now an option for verifying the Guest User. You need TrueCaller SDK `aar` file and PartnerKey. You will get PartnerKey for your app from TrueCaller developer console and need to add it in your `AndroidManifest.xml`. Please find the example below :
```java
<meta-data android:name="com.truecaller.android.sdk.PartnerKey" android:value="@strings/YOUR_TRUECALLER_PARTNER_KEY"/>
```
To add TrueCaller SDK AAR file, go to AndroidStudio's File menu :
New -> New Module -> Select Import AAR/JAR Package option -> Select the provided TrueCaller SDK AAR file.

<a name="moving-from-390---400"></a>
## Moving from 3.9.0 → 4.0.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:4.0.0-40178'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:4.0.0-40178'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:4.0.0-40178'
```


- **BREAKING:** `UserPersonaAnalyticCallback` interface is now removed.
- **BREAKING:** The methods `isBannerVisible()` & `setBannerVisibility(boolean visibility)` of `InboxView` are now removed.
- **BREAKING:** The custom attribute `showBanner` for `InboxView` is now removed.
- Added a new method `launchChannelAndTriggerBot()` in `Router`. This method will launch a channel and trigger bot to perform a specific task.

<a name="moving-from-400---410"></a>
## Moving from 4.0.0 → 4.1.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:4.1.0-41180'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:4.1.0-41180'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:4.1.0-41180'
```

- **BREAKING:** `NotificationManager`class for Haptik SDK is now renamed to `HaptikNotificationManager`.
- Added support to customize the colors of the App bar layout.
- A new interface `InitDataCallback` is added. Clients will implement this interface in Application class and override its single method to perform HaptikLib settings and return InitData reference,
if they are planning not to initialize Haptik SDK in `Application.onCreate()`.
- Added the support for phone number validation during the sign up process, now passing invalid numbers during the sign up
  process will throw a IllegalStateException

<a name="moving-from-410---421"></a>
## Moving from 4.1.0 → 4.2.1
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:4.2.1-42280'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:4.2.1-42280'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:4.2.1-42280'
```
- Updated the image loading library `Glide` version to 4.4.0.

<a name="moving-from-421---430"></a>
## Moving from 4.2.1 → 4.3.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
compile 'ai.haptik.android.sdk:haptiklib-core:4.3.0-43180'
```

```java
Haptik core SDK with cab functionality
compile 'ai.haptik.android.sdk:haptiklib-cab:4.3.0-43180'
```

```java
Haptik core SDK with payment functionality
compile 'ai.haptik.android.sdk:haptiklib-payment:4.3.0-43180'
```
- Updated the AmazonPay SDK to newer version which has bug fixes.
- Changes made to ensure `WAKE_LOCK` are reduced.

<a name="moving-from-430---440"></a>
## Moving from 4.3.0 → 4.4.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:4.4.0-44180'
```

```java
Haptik core SDK with cab functionality
implementation 'ai.haptik.android.sdk:haptiklib-cab:4.4.0-44180'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:4.4.0-44180'
```

- PhonePe SDK is now updated to their new Intent based SDK.
- **BREAKING:** Please **remove the below maven code** from your root build.gradle's respository
```java
maven {
        url "http://phonepe.bintray.com/PhonePeThinAndroidSDK"
        credentials {
            username 'USERNAME'
            password 'PASSWORD'
        }
}
```
and **replace it** with the following:
```java
maven {
    url  "https://phonepe.bintray.com/PhonePeIntentSDK"
}
```
- Please add the following lines in your `AndroidManifest.xml` to test PhonePe on staging environment
```java
<!-- Keep it true in testing environment for PhonePe-->
<meta-data android:name="com.phonepe.android.sdk.isUAT"
        android:value="true" />
```
and **remove** the following:
```java
<meta-data android:name="com.phonepe.android.sdk.AppId"
    android:value="PHONEPE-ID" />
```

<a name="moving-from-440---451"></a>
## Moving from 4.4.0 → 4.5.1
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:4.5.1-45281'
```

```java
Haptik core SDK with cab functionality
implementation 'ai.haptik.android.sdk:haptiklib-cab:4.5.1-45281'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:4.5.1-45281'
```

Now the `userPhone` in `SignUpData.Builder` class is an optional field while signing up on Haptik SDK.

- **BREAKING:** `authId` in `SignUpData.Builder` class is now a **mandatory** field if the `AUTH_TYPE` is other than `BASIC`. If your unique user-id is phone number, please pass the phone number here.

- **BREAKING** Client will have to add a auth module `haptik-guest-auth` or `tilsso-guest-auth` to verify a guest user. Or the clients will have to implement the `VerifyUserService` to add their own user verification system. **Without this user will not be able to access the restricted channels**

- Since Google is blocking apps to read SMS's, the `SMS_RECEIVE` permission is removed and SMSRetriever SDK is used instead for OTP verification of guest user.

- **BREAKING** `signUpViaSso(@NonNull final Callback<User> userCallback)` has now been removed from the Haptik SDK.

<a name="moving-from-451---461"></a>
## Moving from 4.5.1 → 4.6.1
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:4.6.1-46283'
```

```java
Haptik core SDK with cab functionality
implementation 'ai.haptik.android.sdk:haptiklib-cab:4.6.1-46283'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:4.6.1-46283'
```

- **BREAKING:** Updated the play services to 15.0.1.
- **BREAKING:** Updated the firebase core to 16.0.0 and firebase messaging to 17.3.0.
- **BREAKING:** Updated the google-services to 4.1.0.
- Chat transferred from bot to human or chat marked as completed will now be displayed to user.

<a name="moving-from-461---471"></a>
## Moving from 4.6.1 → 4.7.0
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:4.7.0-47183'
```

```java
Haptik core SDK with cab functionality
implementation 'ai.haptik.android.sdk:haptiklib-cab:4.7.0-47183'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:4.7.0-47183'
```

- If the `payment` module is not added, when user taps on recharge screen they will be redirected to the messaging screen after verification, if required.
- **BREAKING:** `TransactionRequestor` class has now been moved to the `payment` module.
- **BREAKING:** `Transaction` class has now been moved to the `payment` module.
- If run time environment is set to `Staging` it will be displayed as a subtitle of the toolbar in the messaging screen.
- Added a `DefaultInboxActivity` which implement `InboxView`. You can use this activity if you do not want major customization in the inbox screen. You can simply call `Router.signUpAndLaunchInbox()` or `Router.launchInbox()` for starting this activity.
- Added new methods in `Router` for quick SDK integration. You can now simply call `Router.signUpAndLaunchChannel()` and `Router.signUpAndLaunchInbox()` with `SignUpData` object to perform user sign-up, SDK will take care of all sync and signup processes. See `QuickStart` doc for more information.

<a name="moving-from-470---501"></a>
## Moving from 4.7.1 → 5.0.1
- After this update add Haptik’s dependencies as below,

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:5.0.1-50283'
```

```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.0.1-50283'
```

```java
Haptik core SDK with cab functionality
implementation 'ai.haptik.android.sdk:haptiklib-cab:5.0.1-50283'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.0.1-50283'
```

- **BREAKING:** Now, the `InboxView` and `Reminders` functionality is segregated into a different `extensions` module. So, if you're using inbox or reminders functionality you need to add new module as below :
```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.0.1-50283'
```

- **BREAKING** Use the following code for importing InboxView :
```xml
<ai.haptik.android.sdk.extensions.inbox.InboxView
      android:id="@+id/inbox"
      android:layout_width="match_parent"
      android:layout_height="match_parent"/>
```

- **BREAKING** Haptik SDK artifactory URL is changed. Please use the one given below :
```java
maven {
    url "https://artifactory.hellohaptik.com/artifactory/libs-release-local"
    credentials {
        username "<ASK HAPTIK FOR USERNAME>"
        password "<ASK HAPTIK FOR PASSWORD>"
    }
}
```

## Moving from 5.0.1 → 5.1.0

- **BREAKING:** If you are using `tilauth` Haptik SDK, the supporting **Truecaller** SDK has been updated to version `0.7`. Please find the updated Truecaller SDK AAR file in the Google Drive shared with you.
- **BREAKING:** The callback `onTaskBoxItemClicked(Task task)` from `MessagingEventListener` is now removed. Please update the listener if you are using it anywhere.
- **BREAKING:** Removed the `til core` and `til dmp` support from the Haptik SDK

## Moving from 5.1.0 → 5.2.0

- **BREAKING:** Add, Edit and Delete address functionality should be accessed from the `extensions` module.
- **BREAKING:** Removed `tilsso-guest-auth` module and truecaller support.

## Moving from 5.2.0 → 5.3.0
- **BREAKING:** Added support for voice feature. See (here)[#voice-support].
- **BREAKING:** Added support for language feature. See (here)[#language-support].

## Moving from 5.3.0 → 5.4.0
```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:5.4.0-54183'
```

```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.4.0-54183'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.4.0-54183'
```

- **BREAKING:** Removed cabs support from Haptik SDK.
- **BREAKING:** Add one of the following dependency, it will be used for
  image loading
    
```java
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:5.4.0-54183'
```
                            OR 
```java
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:5.4.0-54183'
```

- **BREAKING:** Make the following changes to `InitData`
```java
InitData initData = new InitData.Builder(application)
            .baseUrl("https://staging.hellohaptik.com")
            .debugEnabled(true)
            .notificationSound(R.raw.notification_sound)
            .imageLoadingService(`PicassoApiFactory.getPicassoApi()` or `GlideApiFactory.getGlideApi()`) //depending upon the image loading module added in the project
            .build();
``` 
## Moving from 5.4.0 → 5.5.0
- **BREAKING:** Removed deprecated place picker library with Google Places SDK. You now need to add Places SDK API key in your manifest like
```
<meta-data android:name="ai.haptik.places.sdk.api.key"
        android:value="YOUR PLACES SDK API KEY HERE" />
```
- Updated firebase library to 16.0.6.
- Updated firebase messaging library to 17.6.0.

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:5.5.0-55183'
```

```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.5.0-55183'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.5.0-55183'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:5.5.0-55183'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:5.5.0-55183'
```

## Moving from 5.5.0 → 5.5.1

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:5.5.1-55283'
```

```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.5.1-55283'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.5.1-55283'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:5.5.1-55283'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:5.5.1-55283'
```

## Moving from 5.5.1 → 5.6.0
- Removed referral feature.

- Added a module for `Jio` communication bridge, please read the section
  Integrating Jio Communications Module for further details

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:5.6.0-56183'
```

```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.6.0-56183'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.6.0-56183'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:5.6.0-56183'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:5.6.0-56183'
```

```java 
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:5.6.0-56183'
```

## Moving from 5.6.0 → 5.6.1
- Removed referral feature.

- Added a module for `Jio` communication bridge, please read the section
  Integrating Jio Communications Module for further details

```java
Haptik core SDK functionality
implementation 'ai.haptik.android.sdk:haptiklib-core:5.6.1-56283'
```

```java
Haptik core SDK with reminder and inbox functionality
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.6.1-56283'
```

```java
Haptik core SDK with payment functionality
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.6.1-56283'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:5.6.1-56283'
```

```java
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:5.6.1-56283'
```

```java 
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:5.6.1-56283'
```


## Moving from 5.6.1 → 5.7.0
- Actions can now be auto launched from the SDK
- Add support for native TTS
- Moved to AndroidX libraries.

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:5.7.0-57183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:5.7.0-57183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-payment:5.7.0-57183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:5.7.0-57183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:5.7.0-57183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:5.7.0-57183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:5.7.0-57183'
```

## Moving from 5.7.0 → 6.0.0
- Payments are no longer supported by Haptik SDK

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.0.0-60183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.0.0-60183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.0.0-60183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.0.0-60183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.0.0-60183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.0.0-60183'
```

## Moving from 6.0.0 → 6.1.0
- Payments are no longer supported by Haptik SDK

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.1.0-61183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.1.0-61183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.1.0-61183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.1.0-61183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.1.0-61183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.1.0-61183'
```

## Moving from 6.1.0 → 6.2.0

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.2.0-62183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.2.0-62183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.2.0-62183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.2.0-62183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.2.0-62183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.2.0-62183'
```


## Moving from 6.2.0 → 6.2.1

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.2.1-62283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.2.1-62283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.2.1-62283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.2.1-62283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.2.1-62283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.2.1-62283'
```

## Moving from 6.2.1 → 6.3.0

- **BREAKING:** Glide image loading library is updated to v4.11.0.
- CleverTap is disabled by default
- Add capability to upload word documents, pdf etc along with images
- Fixed a crash on devices below Android 5 caused by feedback feature
- Share and Rate options are now configurable. Check https://hellohaptik.github.io/haptik-android-lib/core-module-integration#6-share-functionality.

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.3.0-63183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.3.0-63183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.3.0-63183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.3.0-63183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.3.0-63183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.3.0-63183'
```

## Moving from 6.3.0 → 6.4.2
- Fix a crash caused during image upload for OnePlus devices on Android 10
- Fix a bug related to Forms and Keyboard
- Bug fix related to downloading of document files received from IVA.

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.4.2-64383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.4.2-64383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.4.2-64383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.4.2-64383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.4.2-64383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.4.2-64383'
```

## Moving from 6.4.2 → 6.5.1
- BREAKING: Important security update. Old SDK might not work after 27th July 2020.


```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.5.1-65283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.5.1-65283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.5.1-65283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.5.1-65283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.5.1-65283'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.5.1-65283'
```


## Moving from 6.5.2 → 6.5.3
```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.5.3-65483'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.5.3-65483'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.5.3-65483'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.5.3-65483'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.5.3-65483'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.5.3-65483'
```

## Moving from 6.5.3 → 6.5.4
```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:6.5.4-65583'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:6.5.4-65583'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:6.5.4-65583'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:6.5.4-65583'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:6.5.4-65583'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:6.5.4-65583'
```

## Moving from 6.5.4 → 7.0.0
- **BREAKING:** Min SDK version for Android supported is now 21.

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:7.0.0-70183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:7.0.0-70183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:7.0.0-70183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:7.0.0-70183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:7.0.0-70183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:7.0.0-70183'
```

## Moving from 7.0.0 → 7.0.1

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:7.0.1-70284'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:7.0.1-70284'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:7.0.1-70284'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:7.0.1-70284'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:7.0.1-70284'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:7.0.1-70284'
```

## Moving from 7.0.1 → 7.0.2
- Fixes a bug where the feedback from the user was attributed to a wrong agent
- Fixes a crash caused on the logout event for the SDK
- **BREAKING:** Method signature for logout method has changed.
- **BREAKING:** Implementation of InitDataCallback is no longer optional, please implement the interface in the application class.

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:7.0.2-70383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:7.0.2-70383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:7.0.2-70383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:7.0.2-70383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:7.0.2-70383'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:7.0.2-70383'
```

## Moving from 7.0.2 -> 7.1.0
- Fixed few UI bugs related to QR and Carousal.

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-core:7.1.0_71183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-extensions:7.1.0_71183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-picasso-helper:7.1.0_71183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-glide-helper:7.1.0_71183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-jio-communications:7.1.0_71183'
```

```groovy
implementation 'ai.haptik.android.sdk:haptiklib-xdk:7.1.0_71183'