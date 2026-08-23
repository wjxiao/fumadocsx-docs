# iOS SDK API 参考 (/docs/ios-sdk/api-reference)



# API 参考 [#api-参考]

## IVCSDK [#ivcsdk]

```swift
class IVCSDK {
    static func configure(clientId: String, environment: Environment)
    static func auth() -> AuthManager
    static func vehicle() -> VehicleManager
    static func control() -> ControlManager
}
```

## AuthManager [#authmanager]

```swift
class AuthManager {
    func login(phone: String) async throws -> Result<UserSession, IVCError>
    func logout() async throws
    func refreshToken() async throws
}
```

## VehicleManager [#vehiclemanager]

```swift
class VehicleManager {
    func getVehicles() -> AsyncThrowingStream<[Vehicle], Error>
    func bind(vin: String) async throws -> Vehicle
    func unbind(vehicleId: String) async throws
}
```

## ControlManager [#controlmanager]

```swift
class ControlManager {
    func lock(vehicleId: String) -> AsyncThrowingStream<ControlResult, Error>
    func unlock(vehicleId: String) -> AsyncThrowingStream<ControlResult, Error>
    func setClimate(vehicleId: String, temperature: Double) -> AsyncThrowingStream<ControlResult, Error>
}
```
