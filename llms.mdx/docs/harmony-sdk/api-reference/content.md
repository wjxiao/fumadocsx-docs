# 鸿蒙 SDK API 参考 (/docs/harmony-sdk/api-reference)



# API 参考 [#api-参考]

## IVCSDK [#ivcsdk]

```typescript
interface IVCSDK {
  static init(config: SDKConfig): void;
  static auth(): AuthManager;
  static vehicle(): VehicleManager;
  static control(): ControlManager;
}
```

## AuthManager [#authmanager]

```typescript
interface AuthManager {
  login(phone: string): Promise<Result<UserSession>>;
  logout(): Promise<void>;
}
```

## VehicleManager [#vehiclemanager]

```typescript
interface VehicleManager {
  getVehicles(): Observable<Vehicle[]>;
  bind(vin: string): Promise<Vehicle>;
}
```

## ControlManager [#controlmanager]

```typescript
interface ControlManager {
  lock(vehicleId: string): Observable<ControlResult>;
  unlock(vehicleId: string): Observable<ControlResult>;
}
```
