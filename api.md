# 阿里云镜像市场 API 接口文档
> 以下列出的API均为[阿里云云服务器 ECS Open API](https://api.aliyun.com/api/Ecs/2014-05-26)
## GPU 主机管理

### 创建实例
- **CreateInstance**
  - 功能：创建新的GPU实例
  
### 查询实例
- **DescribeInstanceStatus**
  - 功能：查询实例的简单状态信息
  
- **DescribeInstances** 
  - 功能：查询实例的详细信息
  
- **DescribeInstanceAttribute**
  - 功能：查询指定实例的属性信息

### 重启实例
- **RebootInstance**
  - 功能：重启一台ECS实例
  
- **RebootInstances**
  - 功能：批量重启多台实例

### 删除实例
- **DeleteInstance**
  - 功能：删除单台实例
  
- **DeleteInstances**
  - 功能：批量删除多台实例

## 镜像管理

### 创建镜像
- **CreateImage**
  - 功能：创建自定义镜像
  - 说明：复制一个地域下的自定义镜像到其他地域，可实现跨地域部署ECS实例、跨地域复制ECS实例等目的

### 查询镜像
- **DescribeImages**
  - 功能：查询镜像列表
  - 参数：
    - `ImageOwnerAlias = self`：查询私有镜像
    - `ImageOwnerAlias = system`：查询官方镜像

### 复制镜像
- **CopyImage**
  - 功能：跨地域复制镜像

### 删除镜像
- **DeleteImage**
  - 功能：删除自定义镜像

## 镜像共享

### 共享管理
- **ModifyImageSharePermission**
  - 功能：管理镜像共享权限
  - 说明：可将自定义镜像共享给其他阿里云账号，也可发布为社区镜像供他人使用
  - 支持操作：
    - 共享镜像
    - 取消共享

## 计费管理

### 计费方式
- **支持模式**：按小时和按量的实时出账

### 计费修改
- **ModifyInstanceChargeType**
  - 功能：修改实例计费方式

### 计费查询
- **DescribePrice**
  - 功能：查询指定资源的最新价格
  - 说明：支持根据资源类型查询ECS实例、云盘、专有宿主机、弹性保障服务、容量预定服务的最新价格，包括活动规则、价格、折扣等信息

#### 按量付费查询示例
```json
{
  "RegionId": "cn-hangzhou",
  "ImageId": "aliyun_3_x64_20G_alibase_20221102.vhd",
  "InstanceType": "ecs.g7.large",
  "SystemDisk.Category": "cloud_essd",
  "SystemDisk.Size": 40,
  "DataDisk": [
    {
      "Category": "cloud_essd",
      "Size": 100
    }
  ],
  "InternetMaxBandwidthOut": 10
}
```

#### 按小时付费查询示例
```json
{
  "RegionId": "cn-hangzhou",
  "ImageId": "aliyun_3_x64_20G_alibase_20221102.vhd",
  "InstanceType": "ecs.g7.large",
  "SystemDisk.Category": "cloud_essd",
  "SystemDisk.Size": 40,
  "DataDisk": [
    {
      "Category": "cloud_essd",
      "Size": 100
    }
  ],
  "InternetMaxBandwidthOut": 10,
  "PriceUnit": "Hour",
  "Period": 1
}
```

**参数说明：**
- `PriceUnit`: 价格单位，按小时计费时设置为 "Hour"
- `Period`: 计费时长，云服务器ECS的计费时长为1

