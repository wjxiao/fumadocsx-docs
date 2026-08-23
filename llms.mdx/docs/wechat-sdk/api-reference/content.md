# 微信 SDK API 参考 (/docs/wechat-sdk/api-reference)



# API 参考 [#api-参考]

## IVCSDK [#ivcsdk]

```typescript
interface IVCSDK {
  static init(config: WechatSDKConfig): void;
  static auth(): AuthManager;
  static vehicle(): VehicleManager;
}
```

## AuthManager [#authmanager]

```typescript
interface AuthManager {
  loginWithPhone(encryptedData: string, iv: string): Promise<UserSession>;
  checkSession(): Promise<boolean>;
}
```

## VehicleManager [#vehiclemanager]

```typescript
interface VehicleManager {
  getList(): Promise<Vehicle[]>;
  getDetail(vehicleId: string): Promise<VehicleDetail>;
  bind(vin: string, ownerCode: string): Promise<void>;
}
```
