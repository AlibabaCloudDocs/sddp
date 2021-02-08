# ModifyDataLimit

调用ModifyDataLimit修改SDDP连接授权的配置项。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Sddp&api=ModifyDataLimit&type=RPC&version=2019-01-03)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDataLimit|需要执行的操作。

 取值：**ModifyDataLimit**。 |
|Id|Long|是|11|SDDP连接授权的配置项所属产品的数据资产的唯一标识ID。

 **说明：** 修改SDDP连接授权的配置项时，需要提供其所属产品的数据资产的唯一标识ID，可调用[DescribeDataLimits](~~141637~~)接口获取。 |
|ResourceType|Integer|是|1|SDDP连接授权的配置项数据所属产品的名称。取值：

 -   **1**：MaxCompute
-   **2**：OSS
-   **5**：RDS |
|Lang|String|否|zh|请求和返回消息的语言类型。取值：

 -   **zh**：中文
-   **en**：英文 |
|ServiceRegionId|String|否|cn-hangzhou|资产所在的区域。取值：

 -   **cn-beijing**：华北2 （北京）
-   **cn-zhangjiakou**：华北3（张家口）
-   **cn-huhehaote**：华北5 （呼和浩特）
-   **cn-hangzhou**：华东1 （杭州）
-   **cn-shanghai**：华东2（上海）
-   **cn-shenzhen**：华南1 （深圳）
-   **cn-hongkong**：中国香港 |
|UserName|String|否|tstst|SDDP连接授权RDS数据库的用户名称。 |
|Password|String|否|\*\*\*|SDDP连接授权RDS数据库的用户密码。 |
|ModifyPassword|Boolean|否|true|是否修改连接数据库的用户名和密码，取值：

 -   **true**：修改
-   **false**：不修改 |
|AuditStatus|Integer|否|1|是否开启审计。取值：

 -   **0**：不开启审计
-   **1**：开启审计 |
|LogStoreDay|Integer|否|30|开启审计之后，原始日志的保存时间（单位：天）。取值：

 -   **30**
-   **90**
-   **180**
-   **365** |
|EngineType|String|否|MySQL|数据库类型。取值：

 -   **MySQL**
-   **SQLServer** |
|Port|Integer|否|3306|数据库连接端口。 |
|AutoScan|Integer|否|1|是否在规则发生变更时，自动触发重新扫描。取值：

 -   **0**：不触发自动扫描
-   **1**：触发自动扫描

 **说明：** 规则变更触发自动扫描时，会对数据源中的所有数据进行全量扫描。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|7C3AC882-E5A8-4855-BE77-B6837B695EF1|阿里云为该请求生成的唯一标识符。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifyDataLimit
&Id=11
&ResourceType=1
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyDataLimitResponse>
      <RequestId>7C3AC882-E5A8-4855-BE77-B6837B695EF1</RequestId>
</ModifyDataLimitResponse>
```

`JSON` 格式

```
{
	"RequestId":"7C3AC882-E5A8-4855-BE77-B6837B695EF1"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Sddp)查看更多错误码。

