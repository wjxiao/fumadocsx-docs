# 微信 SDK 快速开始 (/docs/wechat-sdk/quickstart)



# 快速开始 [#快速开始]

## 1. 安装 [#1-安装]

```bash
npm install ivc-weapp-sdk
```

## 2. 初始化 [#2-初始化]

```javascript
// app.js
import { IVCSDK } from 'ivc-weapp-sdk';

App({
  onLaunch() {
    IVCSDK.init({ clientId: 'your_client_id', env: 'staging' });
  },
});
```

## 3. 获取车辆状态 [#3-获取车辆状态]

```javascript
import { IVCSDK } from 'ivc-weapp-sdk';

Page({
  async onLoad() {
    const vehicles = await IVCSDK.vehicle().getList();
    this.setData({ vehicles });
  },
});
```
