# API概览

数据安全中心（DSC）提供以下相关API接口。

## 安全配置

|API|描述|
|---|--|
|[CreateConfig](/intl.zh-CN/API参考/安全配置/CreateConfig.md)|调用本接口修改异常告警通用配置模块的参数。|
|[ModifyDefaultLevel](/intl.zh-CN/API参考/安全配置/ModifyDefaultLevel.md)|调用本接口修改敏感数据的风险等级定义规则，包括未能识别数据的默认风险等级、归类为“敏感”的数据风险等级。|
|[CreateRule](/intl.zh-CN/API参考/安全配置/CreateRule.md)|调用本接口创建自定义的敏感数据识别规则。|
|[ModifyDataLimit](/intl.zh-CN/API参考/安全配置/ModifyDataLimit.md)|调用本接口修改DSC连接授权的配置项。目前仅支持修改RDS的授权配置项，例如；用户名和密码。|
|[ModifyRuleStatus](/intl.zh-CN/API参考/安全配置/ModifyRuleStatus.md)|调用本接口开启或关闭DSC的敏感数据识别规则的检测功能。|
|[ModifyRule](/intl.zh-CN/API参考/安全配置/ModifyRule.md)|调用本接口修改DSC中自定义的敏感数据识别规则。|
|[DescribeDataLimits](/intl.zh-CN/API参考/安全配置/DescribeDataLimits.md)|调用本接口查询DSC连接授权的实例、库、Bucket数据资产列表。|
|[DeleteDataLimit](/intl.zh-CN/API参考/安全配置/DeleteDataLimit.md)|调用本接口删除DSC连接授权的库、实例、Bucket数据资产。|
|[DescribeConfigs](/intl.zh-CN/API参考/安全配置/DescribeConfigs.md)|调用本接口查询异常告警通用配置模块中配置项的列表。|
|[DeleteRule](/intl.zh-CN/API参考/安全配置/DeleteRule.md)|调用本接口删除DSC中自定义的敏感数据识别规则。|
|[DescribeDataLimitDetail](/intl.zh-CN/API参考/安全配置/DescribeDataLimitDetail.md)|调用本接口查询DSC连接授权的单个实例、库、Bucket的详情。|
|[DescribeRules](/intl.zh-CN/API参考/安全配置/DescribeRules.md)|调用本接口查询DSC中敏感数据识别规则的列表。|

## 敏感数据识别

|API|描述|
|---|--|
|[DescribeDataAssets](/intl.zh-CN/API参考/敏感数据识别/DescribeDataAssets.md)|调用本接口执行数据安全中心概览页面的数据资产搜索操作。|
|[DescribeColumns](/intl.zh-CN/API参考/敏感数据识别/DescribeColumns.md)|调用本接口查询DSC连接授权的MaxCompute、RDS的数据资产表中列的数据。|
|[DescribeInstances](/intl.zh-CN/API参考/敏感数据识别/DescribeInstances.md)|调用本接口获取DSC连接授权的MaxCompute、RDS、OSS数据资产实例列表。|
|[DescribeTables](/intl.zh-CN/API参考/敏感数据识别/DescribeTables.md)|调用本接口查询DSC连接授权的MaxCompute、RDS的数据资产表信息。|
|[DescribeOssObjects](/intl.zh-CN/API参考/敏感数据识别/DescribeOssObjects.md)|调用本接口查询DSC连接授权的OSS的存储对象列表。|
|[DescribePackages](/intl.zh-CN/API参考/敏感数据识别/DescribePackages.md)|调用本接口查询已完成扫描授权的MaxCompute数据包的信息，例如数据包的名称、数据包所属者的账号、数据包的风险等级等。|
|[DescribeOssObjectDetail](/intl.zh-CN/API参考/敏感数据识别/DescribeOssObjectDetail.md)|调用本接口查询DSC连接授权的OSS的单个存储对象的详情列表。|

## 异常事件处理

|API|描述|
|---|--|
|[ModifyEventTypeStatus](/intl.zh-CN/API参考/异常事件处理/ModifyEventTypeStatus.md)|调用本接口开启DSC检测子类型异常事件的功能。|
|[DescribeEvents](/intl.zh-CN/API参考/异常事件处理/DescribeEvents.md)|调用本接口查询异常事件列表。|
|[DescribeEventDetail](/intl.zh-CN/API参考/异常事件处理/DescribeEventDetail.md)|调用本接口查询单个异常事件详情，包括异常事件发生时间、异常描述及处理状态等。|
|[ModifyEventStatus](/intl.zh-CN/API参考/异常事件处理/ModifyEventStatus.md)|调用本接口处理异常事件。|
|[DescribeEventTypes](/intl.zh-CN/API参考/异常事件处理/DescribeEventTypes.md)|调用本接口查询异常事件类型的列表。|

