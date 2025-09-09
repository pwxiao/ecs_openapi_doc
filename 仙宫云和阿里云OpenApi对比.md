# API Playground Demo接口与阿里云BSS OpenAPI对应接口对比

| API Playground Demo接口 | 阿里云BSS OpenAPI对应接口 | 备注 |
|---|---|---|
| **实例API** | | |
| 获取实例列表 (GET `/open/instances`) | `QueryAvailableInstances` | 功能上基本一致，都用于查询用户可用的实例列表。 |
| 获取单个实例信息 (GET `/open/instance/{id}`) | `DescribeInstances` | 通常通过各产品线的API（如ECS的`DescribeInstances`）实现。 |
| 获取实例储存的镜像 (GET `/open/instance/{id}/images`) | `DescribeImages` | 镜像管理通常由各产品线的API（如ECS的`DescribeImages`）提供。 |
| 部署实例 (POST `/open/instance/deploy`) | `RunInstances` |  用于批量创建ECS实例，支持自动启动、分配公网IP及设置自动释放时间。 |
| 销毁实例 (POST `/open/instance/destroy`) | `ReleaseInstance` 和 `RefundInstance` | API Playground的“销毁实例”可能涵盖了释放和退订的综合操作。 |
| 关机保留GPU (POST `/open/instance/shutdown`) | `StopInstance` | `StoppedMode=KeepCharging`  |
| 关机释放GPU (POST `/open/instance/shutdown_release_gpu`) | `StopInstance` | `StoppedMode=StopCharging` 计算资源(vCPU、内存、GPU)、镜像 License 费用、固定公网 IP 的固定带宽模式暂停计费 |
| 关机并销毁 (POST `/open/instance/shutdown_destroy`) | `DeleteInstance` |  无 |
| 开机 (POST `/open/instance/boot`) | `StartInstance` | 实例的开机操作通常由各产品线的API（如ECS的`StartInstance`）提供。 |
| 储存镜像 (POST `/open/instance/saveimage`) | 无 | 无
| 储存镜像并销毁 (POST `/open/instance/saveimage_destroy`) | 无 | 无 |
| **私有镜像API** | | |
| 获取镜像列表 (GET `/open/images`) | `DescribeImages` | 阿里云BSS OpenAPI中没有直接对应的私有镜像管理API，通常由具体云产品（如ECS的`DescribeImages`）提供。 |
| 获取镜像信息 (GET `/open/image/{id}`) | 无 | 无 |
| 销毁镜像 (POST `/open/image/destroy`) | `DeleteImageComponent` | 删除自定义镜像 |
<!-- | **账号API** | | |
| 获取用户信息 (GET `/open/whoami`) | 无直接对应接口 | 用户信息的获取通常通过阿里云的RAM或STS等身份认证和授权服务来完成。 |
| 获取账户余额 (GET `/open/balance`) | `QueryAccountBalance` | 属于BSS OpenAPI范畴，用于查询账户余额。 |
| 创建充值订单 (POST `/open/recharge/order`) | `CreateOrder` | 阿里云的`CreateOrder`更为通用和复杂。 |
| 查询充值订单 (GET `/open/recharge/order/{trade_no}`) | `QueryBill` 或 `QueryOrder` | 可以间接查询充值订单状态。 | -->


