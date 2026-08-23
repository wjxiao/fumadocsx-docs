# Android SDK 快速开始 (/docs/android-sdk/quickstart)





# 快速开始 [#快速开始]

## 初始化 SDK [#初始化-sdk]

<Steps>
  <Step title="添加依赖">
    在 `build.gradle.kts` 中添加 SDK 依赖。
  </Step>

  <Step title="初始化">
    ```kotlin
    class MyApplication : Application() {
        override fun onCreate() {
            super.onCreate()
            IVCSdk.init(
                context = this,
                config = SDKConfig(
                    clientId = "your_client_id",
                    environment = Environment.STAGING
                )
            )
        }
    }
    ```
  </Step>

  <Step title="登录">
    ```kotlin
    lifecycleScope.launch {
        val result = IVCSdk.auth().login(phone = "13800138000")
        when (result) {
            is Result.Success -> {
                // 登录成功
            }
            is Result.Error -> {
                // 处理错误
            }
        }
    }
    ```
  </Step>
</Steps>
