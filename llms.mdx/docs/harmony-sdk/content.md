# 鸿蒙 SDK 总览 (/docs/harmony-sdk)





# 鸿蒙 SDK 总览 [#鸿蒙-sdk-总览]

<Callout type="info">
  最低 SDK 版本: API 9 (HarmonyOS 3.0)\
  开发语言: ArkTS\
  包名: `@ivc/sdk`
</Callout>

## 集成方式 [#集成方式]

### ohpm 安装 [#ohpm-安装]

```bash
ohpm install @ivc/sdk
```

## 初始化 [#初始化]

```typescript
import { IVCSDK, Environment } from '@ivc/sdk';

IVCSDK.init({
  clientId: 'your_client_id',
  environment: Environment.STAGING,
});
```
