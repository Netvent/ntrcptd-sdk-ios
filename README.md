# Interceptd SDK
[![alt text](https://app.interceptd.com/static/media/logo.37dfc8d6.svg "Interceptd")](https://interceptd.com/)
## Getting Started
Interceptd SDK targets iOS 10 or higher.

### Using CocoaPods (preferred)
InterceptdSDK is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:
```ruby
pod 'InterceptdSDK'
```
It is also required to set `Always Embed Swift Libraries` to `Yes` from `Build Settings` for projects written in Objective-C
## InterceptdSDK Import
Application needs to import related modules to use InterceptdSDK. Add following lines to `import`’s to achieve this;

```swift
import InterceptdSDK
```
```objc
@import InterceptdSDK;
```
You can check version of SDK with `getSDKVersion` method
```swift
InterceptdAnalytics.getSDKVersion()
```
```objc
[InterceptdAnalytics getSDKVersion];
```
## InterceptdSDK Initialization
InterceptdSDK is required for tracking. Application cannot track any information before InterceptdSDK initialization is complete.
In application’s `didFinishLaunchingWithOptions` callback, call  `InterceptdAnalytics.initialize` function with `applicationId` parameter. This parameter should be your application id from [Interceptd User Dashboard](https://interceptd.com/), you can use your application id for integration purposes. Check following code for sample;
```swift
InterceptdAnalytics.initialize(applicationId: "your-user-id")
```
```objc
[InterceptdAnalytics initialize:@"your-user-id"];
```
## Log Level
InterceptdSDK logging level can be changed with `setLogLevel` after  `InterceptdAnalytics.initialize` call.
```swift
InterceptdAnalytics.setLogLevel(logLevel: .debug)
```
```objc
[InterceptdAnalytics setLogLevel:ASLogLevelDebug];
```
## Custom Event Tracking
Using InterceptdSDK, you are able to track the frequency of custom events by placing the following code piece into your own application code. You can also attach data to your events. If you are planning to attach data to your event, make sure your dictionary is JSON serializable.

```swift
InterceptdAnalytics.track("event-name")
InterceptdAnalytics.track("event-name", data: ["string-key": json-serializable-any, ...])
```
```objc
[InterceptdAnalytics trackWithEventName:@"event-name"];
[InterceptdAnalytics trackWithEventName:@"event-name" data:@{@"string-key": @json-serializable-any, ...}];
```

## Author
Interceptd Mobile Team
## License
Interceptd. All Rights Reserved, 2019
[![alt text](https://app.interceptd.com/static/media/logo.37dfc8d6.svg "Interceptd")](https://interceptd.com/)
