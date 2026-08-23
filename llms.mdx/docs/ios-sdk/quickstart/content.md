# iOS SDK 快速开始 (/docs/ios-sdk/quickstart)



# 快速开始 [#快速开始]

## 1. 安装 SDK [#1-安装-sdk]

通过 Swift Package Manager 或 CocoaPods 安装。

## 2. 初始化 [#2-初始化]

```swift
// AppDelegate.swift
import IVCSDK

@main
class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(_: UIApplication, didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        IVCSDK.configure(clientId: "your_client_id", environment: .staging)
        return true
    }
}
```

## 3. 登录 [#3-登录]

```swift
Task {
    let result = try await IVCSDK.auth().login(phone: "13800138000")
    switch result {
    case .success(let session):
        print("登录成功: \(session.userId)")
    case .failure(let error):
        print("登录失败: \(error.localizedDescription)")
    }
}
```
