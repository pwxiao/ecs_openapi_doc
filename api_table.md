# 阿里云镜像市场 API 接口表格

> 以下列出的API均为[阿里云云服务器 ECS Open API](https://api.aliyun.com/api/Ecs/2014-05-26)

## GPU 主机管理

| 功能 | 接口API | 接口说明 |
|------|---------|----------|
| 创建实例 | [CreateInstance](https://next.api.aliyun.com/api/Ecs/2014-05-26/CreateInstance) | 创建新的GPU实例 |
| 查询实例状态 | [DescribeInstanceStatus](https://next.api.aliyun.com/api/Ecs/2014-05-26/DescribeInstanceStatus) | 查询实例的简单状态信息 |
| 查询实例详细信息 | [DescribeInstances](https://next.api.aliyun.com/api/Ecs/2014-05-26/DescribeInstances) | 查询实例的详细信息 |
| 查询实例属性 | [DescribeInstanceAttribute](https://next.api.aliyun.com/api/Ecs/2014-05-26/DescribeInstanceAttribute) | 查询指定实例的属性信息 |
| 重启单台实例 | [RebootInstance](https://next.api.aliyun.com/api/Ecs/2014-05-26/RebootInstance) | 重启一台ECS实例 |
| 批量重启实例 | [RebootInstances](https://next.api.aliyun.com/api/Ecs/2014-05-26/RebootInstances) | 批量重启多台实例 |
| 删除单台实例 | [DeleteInstance](https://next.api.aliyun.com/api/Ecs/2014-05-26/DeleteInstance) | 删除单台实例 |
| 批量删除实例 | [DeleteInstances](https://next.api.aliyun.com/api/Ecs/2014-05-26/DeleteInstances) | 批量删除多台实例 |

## 镜像管理

| 功能 | 接口API | 接口说明 |
|------|---------|----------|
| 创建镜像 | [CreateImage](https://next.api.aliyun.com/api/Ecs/2014-05-26/CreateImage) | 创建自定义镜像，可实现跨地域部署ECS实例、跨地域复制ECS实例等目的 |
| 查询镜像列表 | [DescribeImages](https://next.api.aliyun.com/api/Ecs/2014-05-26/DescribeImages) | 查询镜像列表，支持查询私有镜像（ImageOwnerAlias=self）和官方镜像（ImageOwnerAlias=system） |
| 复制镜像 | [CopyImage](https://next.api.aliyun.com/api/Ecs/2014-05-26/CopyImage) | 跨地域复制镜像 |
| 删除镜像 | [DeleteImage](https://next.api.aliyun.com/api/Ecs/2014-05-26/DeleteImage) | 删除自定义镜像 |

## 镜像共享

| 功能 | 接口API | 接口说明 |
|------|---------|----------|
| 管理镜像共享权限 | [ModifyImageSharePermission](https://next.api.aliyun.com/api/Ecs/2014-05-26/ModifyImageSharePermission) | 管理镜像共享权限，可将自定义镜像共享给其他阿里云账号，也可发布为社区镜像供他人使用 |

## 计费管理

| 功能 | 接口API | 接口说明 |
|------|---------|----------|
| 修改计费方式 | [ModifyInstanceChargeType](https://next.api.aliyun.com/api/Ecs/2014-05-26/ModifyInstanceChargeType) | 修改实例计费方式，支持按小时和按量的实时出账 |
| 查询资源价格 | [DescribePrice](https://next.api.aliyun.com/api/Ecs/2014-05-26/DescribePrice) | 查询指定资源的最新价格，支持根据资源类型查询ECS实例、云盘、专有宿主机、弹性保障服务、容量预定服务的最新价格，包括活动规则、价格、折扣等信息 |