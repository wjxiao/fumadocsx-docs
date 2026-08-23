# 认证机制 (/docs/cloud-api/authentication)





# 认证机制 [#认证机制]

## OAuth 2.0 流程 [#oauth-20-流程]

<Mermaid
  chart="sequenceDiagram
    participant App as 移动 App
    participant Auth as 认证服务
    participant API as API Gateway

    App->>Auth: 1. 授权请求 (client_id + scope)
    Auth->>Auth: 2. 用户认证
    Auth-->>App: 3. 授权码
    App->>Auth: 4. 换取 Token
    Auth-->>App: 5. Access Token + Refresh Token
    App->>API: 6. API 请求 (Bearer Token)
    API->>Auth: 7. Token 验证
    Auth-->>API: 8. 用户信息
    API-->>App: 9. 响应"
/>

## Token 格式 [#token-格式]

使用 JWT (JSON Web Token)，包含以下声明：

```json
{
  "sub": "user_123456",
  "aud": "ivc-system",
  "exp": 1719000000,
  "iat": 1718913600,
  "scope": "vehicle:read vehicle:write"
}
```

<Tabs>
  <Tab value="header" title="请求头">
    ```
    Authorization: Bearer eyJhbGciOiJSUzI1NiIs...
    ```
  </Tab>

  <Tab value="error" title="错误响应">
    ```json
    {
      "error": "UNAUTHORIZED",
      "message": "Token 已过期",
      "status": 401
    }
    ```
  </Tab>
</Tabs>
