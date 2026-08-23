# 鸿蒙 SDK 快速开始 (/docs/harmony-sdk/quickstart)



# 快速开始 [#快速开始]

## 1. 安装 [#1-安装]

```bash
ohpm install @ivc/sdk
```

## 2. 初始化 [#2-初始化]

```typescript
// entry/src/main/ets/entryability/EntryAbility.ets
import { IVCSDK, Environment } from '@ivc/sdk';

export default class EntryAbility extends UIAbility {
  onCreate() {
    IVCSDK.init({
      clientId: 'your_client_id',
      environment: Environment.STAGING,
    });
  }
}
```

## 3. 登录 [#3-登录]

```typescript
import { IVCSDK } from '@ivc/sdk';

async function login() {
  const result = await IVCSDK.auth().login('13800138000');
  if (result.isSuccess) {
    console.info('登录成功');
  }
}
```
