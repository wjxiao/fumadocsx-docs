# Android SDK API 参考 (/docs/android-sdk/api-reference)



# API 参考 [#api-参考]

## IVCSdk [#ivcsdk]

SDK 主入口类。

### 初始化 [#初始化]

```kotlin
IVCSdk.init(context: Context, config: SDKConfig)
```

### 登录 [#登录]

```kotlin
IVCSdk.auth().login(phone: String): Result<UserSession>
```

## VehicleManager [#vehiclemanager]

### 获取车辆列表 [#获取车辆列表]

```kotlin
IVCSdk.vehicle().getVehicles(): Flow<List<Vehicle>>
```

### 远程控制 [#远程控制]

```kotlin
IVCSdk.control().lock(vehicleId: String): Flow<ControlResult>
IVCSdk.control().unlock(vehicleId: String): Flow<ControlResult>
```
