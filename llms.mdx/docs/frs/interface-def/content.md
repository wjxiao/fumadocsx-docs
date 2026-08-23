# 接口定义 (/docs/frs/interface-def)





# 接口定义 [#接口定义]

## 内部接口 [#内部接口]

### App → 云端 [#app--云端]

<Tabs>
  <Tab value="rest" title="REST API">
    协议: HTTPS\
    格式: JSON\
    认证: Bearer Token\
    基础 URL: `https://api.ivc-system.com/v1`
  </Tab>

  <Tab value="ws" title="WebSocket">
    协议: WSS\
    用途: 实时状态推送\
    心跳: 30 秒\
    重连: 指数退避
  </Tab>
</Tabs>

### 云端 → 车机 [#云端--车机]

| 协议   | 用途   | QoS   |
| ---- | ---- | ----- |
| MQTT | 指令下发 | QoS 1 |
| MQTT | 状态上报 | QoS 0 |

## 接口规范 [#接口规范]

### 通用响应格式 [#通用响应格式]

```json
{
  "code": 0,
  "message": "success",
  "data": {},
  "request_id": "req_xxxxx"
}
```

### 分页参数 [#分页参数]

| 参数    | 类型     | 默认值 | 说明   |
| ----- | ------ | --- | ---- |
| page  | int    | 1   | 页码   |
| limit | int    | 20  | 每页条数 |
| sort  | string | -   | 排序字段 |
| order | string | asc | 排序方向 |
