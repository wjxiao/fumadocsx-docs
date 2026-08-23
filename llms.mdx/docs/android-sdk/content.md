# 安卓 SDK 总览 (/docs/android-sdk)





# 安卓 SDK 总览 [#安卓-sdk-总览]

<Callout type="info">
  最低 SDK 版本: API 26 (Android 8.0)\
  编译 SDK 版本: API 35 (Android 15)\
  包名: `com.ivc.sdk`
</Callout>

## 集成方式 [#集成方式]

### Gradle 依赖 [#gradle-依赖]

```kotlin
dependencies {
    implementation("com.ivc.sdk:ivc-sdk:2.1.0")
}
```

### 权限配置 [#权限配置]

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.BLUETOOTH_CONNECT" />
```

## SDK 架构 [#sdk-架构]

<Mermaid
  chart="flowchart LR
    SDK[IVC SDK] --> Auth[认证模块]
    SDK --> Vehicle[车辆模块]
    SDK --> Control[控制模块]
    SDK --> Nav[导航模块]
    Auth --> API[云端 API]
    Vehicle --> API
    Control --> MQ[MQTT]
    Nav --> API"
/>
