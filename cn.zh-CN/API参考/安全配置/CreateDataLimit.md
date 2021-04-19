# CreateDataLimit

调用CreateDataLimit创建SDDP对数据库、项目、存储空间（Bucket）进行扫描的授权。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Sddp&api=CreateDataLimit&type=RPC&version=2019-01-03)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateDataLimit|需要执行的操作。

 取值：**CreateDataLimit**。 |
|ResourceType|Integer|是|1|授权扫描的资产所属的产品类型。取值：

 -   **1**：MaxCompute
-   **2**：OSS
-   **5**：RDS |
|Lang|String|否|zh|请求和返回消息的语言类型。取值：

 -   **zh**：中文
-   **en**：英文 |
|ServiceRegionId|String|否|cn-hangzhou|资产所在的地域。取值：

 -   **cn-beijing**：华北2 （北京）
-   **cn-zhangjiakou**：华北3（张家口）
-   **cn-huhehaote**：华北5 （呼和浩特）
-   **cn-hangzhou**：华东1 （杭州）
-   **cn-shanghai**：华东2（上海）
-   **cn-shenzhen**：华南1 （深圳）
-   **cn-hongkong**：中国香港 |
|ParentId|String|否|test-11\*\*|资产的名称。 |
|UserName|String|否|yhm|数据库资产的用户名。 |
|Password|String|否|passwd|访问数据库资产的密码。 |
|AuditStatus|Integer|否|1|是否开启审计。取值：

 -   **0**：不开启审计
-   **1**：开启审计 |
|AutoScan|Integer|否|1|是否在规则发生变更时，自动触发重新扫描。取值：

 -   **0**：不触发自动扫描
-   **1**：触发自动扫描

 **说明：** 规则变更触发自动扫描时，会对数据源中的所有数据进行全量扫描。 |
|LogStoreDay|Integer|否|30|指定开启审计之后，原始日志的保存时间（单位：天）。取值：

 -   **30**
-   **90**
-   **180**
-   **365** |
|EngineType|String|否|MySQL|数据库类型。取值：

 -   **MySQL**
-   **SQLServer** |
|Port|Integer|否|3306|数据库连接端口。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Id|Integer|1|授权资源的ID。 |
|RequestId|String|7C3AC882-E5A8-4855-BE77-B6837B695EF1|阿里云为该请求生成的唯一标识符。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=CreateDataLimit
&ResourceType=1
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<CreateDataLimitResponse>
  <Id>1</Id>
  <RequestId>7C3AC882-E5A8-4855-BE77-B6837B695EF1</RequestId>
</CreateDataLimitResponse>
```

`JSON` 格式

```
{
	"Id":1,
	"RequestId":"7C3AC882-E5A8-4855-BE77-B6837B695EF1"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Sddp)查看更多错误码。

