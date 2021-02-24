# DescribeDataAssets

调用DescribeDataAssets接口查询存在敏感数据的资产列表。

****

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Sddp&api=DescribeDataAssets&type=RPC&version=2019-01-03)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDataAssets|需要执行的操作。

 取值：**DescribeDataAssets**。 |
|Lang|String|否|zh|指定请求和接收消息的语言类型，默认为**zh**。取值：

 -   **zh**：中文
-   **en**：英文 |
|Name|String|否|test|指定要查询资产的关键词，支持模糊查询。 |
|RiskLevels|String|否|S1|指定要查询的数据资产的风险等级，存在多个时使用英文逗号（,）隔开。

 -   **S1**：弱风险等级
-   **S2**：中等风险等级
-   **S3**：高风险等级
-   **S4**：最高风险等级 |
|RuleId|Long|否|11122200|指定数据资产命中的敏感数据识别规则唯一标识ID。

 **说明：** 如果根据数据资产命中的敏感数据识别规则来搜索数据资产，敏感数据识别规则的ID可调用[DescribeRules](~~141389~~)接口获取。 |
|RangeId|Integer|否|1|指定要查询的数据资产类型。取值：

 -   **1**：MaxCompute项目
-   **2**：MaxCompute表
-   **3**：MaxCompute包
-   **11**：分析型数据库MySQL（ADS）库
-   **12**：分析型数据库MySQL（ADS）表
-   **21**：OSS文件桶
-   **22**：OSS Object
-   **31**：表格存储实例
-   **32**：表格存储表
-   **51**：RDS库
-   **52**：RDS表
-   **61**：ECS自建数据库
-   **62**：ECS自建数据表
-   **71**：DRDS库
-   **72**：DRDS表
-   **81**：PolarDB库
-   **82**：PolarDB表
-   **91**：GPDB库
-   **92**：GPDB表 |
|PageSize|Integer|否|20|指定分页查询时，每页显示的数据最大条数。每页默认显示的数据条数为20条，PageSize参数值为空时，将默认返回20条数据。

 **说明：** 建议PageSize取值不要为空。 |
|CurrentPage|Integer|否|1|指定分页查询时，当前页的页码。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~141847~~)。

调用API的请求格式，请参见本文示例中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|CurrentPage|Integer|1|分页查询时，当前页的页码。 |
|Items|Array of Asset| |数据资产列表。 |
|Acl|String|private|OSS文件桶的ACL权限设置。 |
|CreationTime|Long|1536751124000|数据资产创建时间，单位为毫秒。 |
|DataType|String|OSS\_BUCKET|数据资产所属的数据类型。 |
|Id|String|268|数据资产的唯一标识ID。 |
|Labelsec|Integer|0|MaxCompute资产的安全标志。 |
|Name|String|gxdata|数据资产名称。 |
|ObjectKey|String|内部|OSS存储对象的Key值。 |
|OdpsRiskLevelName|String|S4|MaxCompute资产的风险等级名称。取值：

 -   **S1**：弱风险等级
-   **S2**：中等风险等级
-   **S3**：高级风险等级
-   **S4**：最高风险等级 |
|Owner|String|dtdep-239-\*\*\*\*\*\*|数据资产所属者账号。 |
|ProductCode|String|RDS|数据资产所属产品名称。

 -   MaxCompute
-   OSS
-   RDS |
|ProductId|String|5|数据资产所属产品类型ID。 |
|Protection|Boolean|false|MaxCompute资产的防护状态。 |
|RiskLevelId|Long|2|数据资产的风险等级ID。 |
|RiskLevelName|String|中等风险等级|数据资产的风险等级名称。 |
|RuleName|String|\*\*\*规则|数据资产命中的敏感数据识别规则名称。 |
|Sensitive|Boolean|true|数据资产中是否包含敏感数据。取值：

 -   **true**：包含
-   **false**：不包含 |
|SensitiveCount|Integer|24|数据资产中敏感数据总数。例如：MaxCompute中敏感的项目、包或表的总数；RDS中敏感的数据库或表的总数；OSS中敏感的文件桶或Object的总数。 |
|SensitiveRatio|String|45%|在所有数据资产中敏感数据所占的比例。 |
|TotalCount|Integer|432|所有数据资产的数量。例如：MaxCompute中项目、包或表的总数；RDS中数据库或表的总数；OSS中文件桶或Object的总数。 |
|PageSize|Integer|20|分页查询时，每页最多显示的数据条数。 |
|RequestId|String|71064826-726F-4ADA-B879-05D8055476FB|阿里云为该请求生成的唯一标识符。 |
|TotalCount|Integer|1|查询到的存在敏感数据的资产总数量。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDataAssets
&RangeId=1
&<公共请求参数>
```

正常返回示例

`XML`格式

```
Response<?xml version="1.0" encoding="UTF-8" ?>
<DescribeDataAssetsResponse>
	<RequestId>71064826-726F-4ADA-B879-05D8055476FB</RequestId>
	<TotalCount>1</TotalCount>
	<PageSize>20</PageSize>
	<CurrentPage>1</CurrentPage>
	<Items>
		<Owner>dtdep-239-******</Owner>
		<ProductCode>RDS</ProductCode>
		<ProductId>5</ProductId>
		<Acl></Acl>
		<RiskLevelId>2</RiskLevelId>
		<RiskLevelName>中等风险等级</RiskLevelName>
		<DepartName>***DemoCenter</DepartName>
		<Name>gxdata</Name>
		<Labelsec>0</Labelsec>
		<CreationTime>1536751124000</CreationTime>
		<Sensitive>true</Sensitive>
		<Id>268</Id>
		<Protection>false</Protection>
		<RuleName>***规则</RuleName>
		<ObjectKey>内部</ObjectKey>
	</Items>
</DescribeDataAssetsResponse>
```

`JSON`格式

```
{
    "RequestId":"71064826-726F-4ADA-B879-05D8055476FB",
    "TotalCount":1,
    "PageSize":20,
    "CurrentPage":1,
    "Items":[
        {
            "Owner":"dtdep-239-******", 
            "ProductCode":"RDS",
            "ProductId":5,
            "Acl":"",
            "RiskLevelId":2,
            "RiskLevelName":"中等风险等级", 
            "DepartName":"***DemoCenter", 
            "Name":"gxdata", 
            "Labelsec":0,
            "CreationTime":1536751124000, 
            "Sensitive":true, 
            "Id":268, 
            "Protection":false, 
            "RuleName":"***规则",
            "ObjectKey":"内部"
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Sddp)查看更多错误码。

