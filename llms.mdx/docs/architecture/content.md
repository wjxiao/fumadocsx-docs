# 架构总览 (/docs/architecture)





# 架构总览 [#架构总览]

<Callout type="info">
  本文档描述智能车联系统的整体架构设计。
</Callout>

## 系统分层 [#系统分层]

<Mermaid
  chart="graph TD
    A[移动端 App] --> B[API Gateway]
    B --> C[微服务集群]
    C --> D[(数据库)]
    C --> E[消息队列]
    E --> F[车机端]
    B --> G[第三方服务]"
/>

## 技术架构 [#技术架构]

<Tabs>
  <Tab value="app" title="移动端">
    * 架构: MVVM + Clean Architecture
    * 网络: Retrofit / URLSession
    * 状态管理: StateFlow / Combine
    * 本地存储: Room / CoreData
  </Tab>

  <Tab value="backend" title="后端">
    * 框架: Spring Boot / Go
    * API 协议: REST + gRPC
    * 数据库: PostgreSQL + Redis
    * 消息队列: Kafka
  </Tab>

  <Tab value="vehicle" title="车机端">
    * 系统: Android Automotive / Linux
    * 通信: MQTT + CAN Bus
    * OTA: AB 分区升级
  </Tab>
</Tabs>

## 项目结构 [#项目结构]

<Files>
  <Folder name="src">
    <Folder name="app">
      <File name="presentation" />

      <File name="domain" />

      <File name="data" />
    </Folder>

    <Folder name="shared">
      <File name="network" />

      <File name="storage" />
    </Folder>
  </Folder>
</Files>
