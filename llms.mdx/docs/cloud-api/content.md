# 云端 API 总览 (/docs/cloud-api)





# 云端 API 总览 [#云端-api-总览]

<Callout type="info">
  所有 API 均需通过 Bearer Token 认证。
  基础 URL: `https://api.ivc-system.com/v1`
</Callout>

## API 列表 [#api-列表]

### 车辆管理 [#车辆管理]

| 方法     | 路径                      | 说明     |
| ------ | ----------------------- | ------ |
| GET    | `/vehicles`             | 获取车辆列表 |
| POST   | `/vehicles/bind`        | 绑定车辆   |
| DELETE | `/vehicles/{id}`        | 解绑车辆   |
| GET    | `/vehicles/{id}/status` | 获取车辆状态 |

### 远程控制 [#远程控制]

| 方法   | 路径                       | 说明   |
| ---- | ------------------------ | ---- |
| POST | `/vehicles/{id}/lock`    | 远程锁车 |
| POST | `/vehicles/{id}/unlock`  | 远程解锁 |
| POST | `/vehicles/{id}/climate` | 空调控制 |

## 错误码 [#错误码]

| 状态码 | 错误码           | 说明    |
| --- | ------------- | ----- |
| 401 | UNAUTHORIZED  | 认证失败  |
| 403 | FORBIDDEN     | 无权限   |
| 404 | NOT\_FOUND    | 资源不存在 |
| 429 | RATE\_LIMITED | 请求限流  |
