# DescribeConfigs

调用本接口查询异常告警通用配置模块中配置项的列表。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Sddp&api=DescribeConfigs&type=RPC&version=2019-01-03)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeConfigs|系统规定参数。取值：DescribeConfigs。 |
|Lang|String|否|zh|请求和接收消息的语言类型。

 -   **zh**：中文
-   **en**：英文 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigList|Array of Config| |异常告警通用配置项列表。 |
|Code|Integer|1|异常告警通用配置模块中配置项的编码。 |
|DefaultValue|String|当日某类日志输出量低于前10天平均值的30%|异常告警通用配置项参数的默认值描述。 |
|Description|String|日志未有效输出|异常告警通用配置项的描述。 |
|Id|Long|2133|异常告警通用配置项的唯一标识ID。 |
|Value|Long|30|异常告警通用配置项的参数值。 |
|RequestId|String|769FB3C1-F4C9-42DF-9B72-7077A8989C13|结果的请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeConfigs
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeConfigs>
  <RequestId>769FB3C1-F4C9-42DF-9B72-7077A8989C13</RequestId>
  <ConfigList>
        <Code>2001</Code>
        <DefaultValue>目前的阈值定义为10次</DefaultValue>
        <Description>当日某类日志输出量低于前10天平均值的30%</Description>
        <Id>2133</Id>
        <Value>10</Value>
  </ConfigList>
</DescribeConfigs>
```

`JSON`格式

```
{
    "RequestId":"769FB3C1-F4C9-42DF-9B72-7077A8989C13",
    "ConfigList":[
        {
            "Code":1, 
            "DefaultValue":"当日某类日志输出量低于前10天平均值的30%",
            "Description":"日志未有效输出", 
            "Id":2133,
            "Value":10
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Sddp)查看更多错误码。

