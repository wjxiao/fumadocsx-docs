# iOS SDK 总览 (/docs/ios-sdk)





# iOS SDK 总览 [#ios-sdk-总览]

<Callout type="info">
  最低部署目标: iOS 15.0\
  Swift 版本: 5.9+\
  包名: `IVCSDK`
</Callout>

## 集成方式 [#集成方式]

### Swift Package Manager [#swift-package-manager]

```
https://github.com/ivc-system/ios-sdk.git
```

### CocoaPods [#cocoapods]

```ruby
pod 'IVCSDK', '~> 2.1.0'
```

## 初始化 [#初始化]

```swift
import IVCSDK

// AppDelegate.swift
IVCSDK.configure(
    clientId: "your_client_id",
    environment: .staging
)
```
