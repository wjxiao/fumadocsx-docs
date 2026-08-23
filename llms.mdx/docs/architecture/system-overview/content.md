# 系统概述 (/docs/architecture/system-overview)



# 系统概述 [#系统概述]

## 系统边界 [#系统边界]

智能车联系统包含以下核心子系统：

1. **云端平台** — 核心业务逻辑与数据存储
2. **移动 App** — 用户交互界面
3. **车机系统** — 车辆数据采集与控制执行
4. **管理后台** — 运维与数据分析

## 通信架构 [#通信架构]

<Mermaid
  chart="sequenceDiagram
    participant App as 移动 App
    participant GW as API Gateway
    participant MS as 微服务
    participant MQ as 消息队列
    participant VC as 车机

    App->>GW: HTTPS/WSS 请求
    GW->>MS: 路由转发
    MS->>MQ: 推送指令
    MQ->>VC: MQTT 推送
    VC-->>MQ: 执行结果
    MQ-->>MS: 消息回调
    MS-->>GW: 响应
    GW-->>App: 请求结果"
/>

## 部署架构 [#部署架构]

| 组件          | 部署方式       | 规格       |
| ----------- | ---------- | -------- |
| API Gateway | K8s (多副本)  | 4C8G x 3 |
| 微服务         | K8s (弹性伸缩) | 2C4G x 5 |
| PostgreSQL  | 云 RDS      | 主从架构     |
| Redis       | 云 Redis    | 集群模式     |
| Kafka       | 云 Kafka    | 3 Broker |
