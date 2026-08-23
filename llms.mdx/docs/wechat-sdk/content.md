# 微信 SDK 总览 (/docs/wechat-sdk)





# 微信 SDK 总览 [#微信-sdk-总览]

<Callout type="info">
  基础库版本: 2.30.0+\
  开发语言: JavaScript / TypeScript\
  npm 包名: `ivc-weapp-sdk`
</Callout>

## 集成方式 [#集成方式]

### npm 安装 [#npm-安装]

```bash
npm install ivc-weapp-sdk
```

### 小程序配置 [#小程序配置]

```json
// app.json
{
  "plugins": {
    "ivc-sdk": {
      "version": "2.1.0",
      "provider": "wx123456789"
    }
  }
}
```

## 初始化 [#初始化]

```javascript
import { IVCSDK } from 'ivc-weapp-sdk';

// app.js
App({
  onLaunch() {
    IVCSDK.init({
      clientId: 'your_client_id',
      env: 'staging',
    });
  },
});
```
