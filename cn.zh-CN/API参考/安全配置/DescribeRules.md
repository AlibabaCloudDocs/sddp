# DescribeRules

调用本接口查询SDDP中敏感数据识别规则的列表。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Sddp&api=DescribeRules&type=RPC&version=2019-01-03)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRules|系统规定参数。取值：DescribeRules。 |
|Category|Integer|否|2|敏感数据识别规则内容的类型。

 -   0：关键字
-   2：正则表达式 |
|CurrentPage|Integer|否|1|分页查询时的页码。 |
|CustomType|Integer|否|1|敏感数据识别规则的类型。

 -   0：表示系统内置
-   1：表示用户自定义 |
|Lang|String|否|zh|请求和接收消息的语言类型。

 -   **zh**：中文
-   **en**：英文 |
|Name|String|否|\*\*\*规则|敏感数据识别规则名称，支持模糊匹配。 |
|PageSize|Integer|否|12|列表每页显示的数据最大条数。 |
|RiskLevelId|Long|否|1|敏感数据识别规则的风险等级ID。

 -   1：S1，弱风险等级。
-   2：S2，中等风险等级。
-   3：S3，高级风险等级。
-   4：S4，最高风险等级。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|CurrentPage|Integer|1|结果中显示的当前页的页码。 |
|Items| | |敏感数据识别规则列表。 |
|Category|Integer|2|敏感数据识别规则内容的类型。

 -   0：关键字
-   2：正则表达式 |
|CategoryName|String|正则表达式|敏感数据识别规则内容所属类型名称。 |
|Content|String|\(?:\\\\D\|^\)\(\(?:\(?:25\[0-4\]\|2\[0-4\]\\\\d\|1\\\\d\{2\}\|\[1-9\]\\\\d\{1\}\)\\\\.\)\(?:\(?:25\[0-5\]\|2\[0-4\]\\\\d\|\[01\]?\\\\d?\\\\d\)\\\\.\)\{2\}\(?:25\[0-5\]\|2\[0-4\]\\\\d\|1\[0-9\]\\\\d\|\[1-9\]\\\\d\|\[1-9\]\)\)\(?:\\\\D\|$\)|敏感数据识别规则的内容。 |
|CustomType|Integer|1|敏感数据识别规则类型。

 -   0：表示系统内置
-   1：表示用户自定义 |
|Description|String|用于识别IP地址|敏感数据识别规则的描述信息。 |
|DisplayName|String|\*\*\*\*test|敏感数据识别规则的创建人账号显示名。 |
|GmtCreate|Long|1545277010000|敏感数据识别规则的创建时间毫秒数。 |
|GmtModified|Long|1545277010000|敏感数据识别规则的修改时间毫秒数。 |
|Id|Long|20000|保存记录的敏感数据识别规则的唯一标识ID。 |
|LoginName|String|det1111|敏感数据识别规则的创建人账号登录名。 |
|Name|String|IP地址|敏感数据识别规则的名称。 |
|RiskLevelId|Long|2|敏感数据识别规则的风险等级ID。

 -   1：S1
-   2：S2
-   3：S3
-   4：S4 |
|RiskLevelName|String|S2|敏感数据识别规则的风险等级名称。

 -   S1：弱风险等级
-   S2：中等风险等级
-   S3：高级风险等级
-   S4：最高风险等级 |
|Status|Integer|1|敏感数据识别规则的检测状态。

 -   0：关闭
-   1：开启 |
|UserId|Long|0|敏感数据识别规则的创建人账号ID。 |
|PageSize|Integer|12|结果中每页显示的数据条数。 |
|RequestId|String|769FB3C1-F4C9-42DF-9B72-7077A8989C13|结果的请求ID。 |
|TotalCount|Integer|23|结果中数据的总条数。 |

## 示例

请求示例

```

http(s)://[Endpoint]/?Action=DescribeRules
&<公共请求参数>

```

正常返回示例

`XML` 格式

```
<DescribeRules>
	  <RequestId>769FB3C1-F4C9-42DF-9B72-7077A8989C13</RequestId>
	  <Items>
		    <Description>用于识别IP地址</Description>
		    <Category>2</Category>
		    <GmtModified>1545277010000</GmtModified>
		    <RiskLevelId>2</RiskLevelId>
		    <Name>IP地址</Name>
		    <GmtCreate>1545277010000</GmtCreate>
		    <UserId>0</UserId>
		    <Status>1</Status>
		    <Content>(?:\D|^)((?:(?:25[0-4]|2[0-4]\d|1\d{2}|[1-9]\d{1})\.)(?:(?:25[0-5]|2[0-4]\d|[01]?\d?\d)\.){2}(?:25[0-5]|2[0-4]\d|1[0-9]\d|[1-9]\d|[1-9]))(?:\D|$)</Content>
		    <CategoryName>正则表达式</CategoryName>
		    <RiskLevelName>S2</RiskLevelName>
		    <DepartName>test</DepartName>
		    <LoginName>det1111</LoginName>
		    <Id>2000</Id>
	  </Items>
	  <TotalCount>18</TotalCount>
	  <PageSize>10</PageSize>
	  <CurrentPage>1</CurrentPage>
</DescribeRules>
```

`JSON` 格式

```
{
	"Items":[
		{
			"Description":"用于识别IP地址",
			"CategoryName":"正则表达式",
			"LoginName":"det1111",
			"RiskLevelId":2,
			"DepartName":"test",
			"UserId":0,
			"GmtCreate":1545277010000,
			"GmtModified":1545277010000,
			"Name":"IP地址",
			"Status":1,
			"Category":2,
			"RiskLevelName":"S2",
			"Id":2000,
			"Content":"(?:\\D|^)((?:(?:25[0-4]|2[0-4]\\d|1\\d{2}|[1-9]\\d{1})\\.)(?:(?:25[0-5]|2[0-4]\\d|[01]?\\d?\\d)\\.){2}(?:25[0-5]|2[0-4]\\d|1[0-9]\\d|[1-9]\\d|[1-9]))(?:\\D|$)"
		}
	],
	"TotalCount":18,
	"PageSize":10,
	"RequestId":"769FB3C1-F4C9-42DF-9B72-7077A8989C13",
	"CurrentPage":1
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Sddp)查看更多错误码。

