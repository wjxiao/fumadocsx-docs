# API 端点 (/docs/cloud-api/endpoints)



# API 端点 [#api-端点]

## 车辆状态 [#车辆状态]

### 获取车辆列表 [#获取车辆列表]

`GET /vehicles`

**请求参数：**

| 参数     | 类型     | 必填 | 说明                   |
| ------ | ------ | -- | -------------------- |
| page   | int    | 否  | 页码，默认 1              |
| limit  | int    | 否  | 每页条数，默认 20           |
| status | string | 否  | 筛选状态: online/offline |

**响应示例：**

```json
{
  "data": [
    {
      "id": "v_001",
      "vin": "LSVAU2A38N2100001",
      "plate": "粤B·88888",
      "status": "online",
      "last_updated": "2026-07-26T10:00:00Z"
    }
  ],
  "total": 1,
  "page": 1,
  "limit": 20
}
```

### 获取车辆状态 [#获取车辆状态]

`GET /vehicles/{id}/status`

**响应示例：**

```json
{
  "vehicle_id": "v_001",
  "timestamp": "2026-07-26T10:00:00Z",
  "battery": {
    "level": 85.5,
    "charging": true
  },
  "location": {
    "latitude": 22.5431,
    "longitude": 114.0579
  },
  "speed": 0,
  "engine": "off"
}
```
