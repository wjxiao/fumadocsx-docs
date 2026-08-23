# 数据流设计 (/docs/architecture/data-flow)





# 数据流设计 [#数据流设计]

## 核心数据流 [#核心数据流]

### 车辆状态上报 [#车辆状态上报]

<Mermaid
  chart="flowchart LR
    VC[车机 CAN Bus] -->|采集| DAU[数据采集单元]
    DAU -->|MQTT| MQ[消息队列]
    MQ -->|消费| SP[流处理]
    SP -->|写入| TS[(时序数据库)]
    TS -->|查询| API[REST API]
    API -->|WebSocket| APP[移动 App]"
/>

## 数据结构 [#数据结构]

<Callout type="info">
  所有时间戳统一使用 UTC 时间，毫秒精度。
</Callout>

### VehicleStatus [#vehiclestatus]

| 字段             | 类型       | 说明            |
| -------------- | -------- | ------------- |
| vehicle\_id    | string   | 车辆 VIN 码      |
| timestamp      | int64    | 数据采集时间戳       |
| battery\_level | float    | 电量百分比 (0-100) |
| speed          | float    | 速度 (km/h)     |
| location       | GeoPoint | GPS 坐标        |
| engine\_status | enum     | 引擎状态          |
