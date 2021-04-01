# ExecDatamask

调用ExecDatamask接口对数据进行动态脱敏。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Sddp&api=ExecDatamask&type=RPC&version=2019-01-03)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ExecDatamask|需要执行的操作。

 取值：**ExecDatamask**。 |
|Data|String|是|\{"dataHeaderList":\["name","age"\],"dataList":\[\["lily",18\],\["lucy",17\]\],"ruleList":\[1002,null\]\}|指定需要脱敏的数据。采用JSON格式的字符串表述，具体结构如下：

 -   **dataHeaderList**：数据的列名，顺序和需要脱敏的数据一一对应。
-   **dataList**：需要脱敏的数据。
-   **ruleList** ：敏感类型ID列表，顺序和需要脱敏的数据一一对应。

敏感类型ID是数字，不同的数字代表不同的敏感类型，可通过[DescribeConfigs](~~141387~~)接口获取。 |
|TemplateId|Long|是|1|指定脱敏模板ID。在[数据安全中心控制台](https://yundun.console.aliyun.com/?&p=sddpnext#/sddp/dm/template)上创建模板后会生成模板ID，您可以在**数据脱敏**\>**脱敏模板**页面获取**脱敏模板ID**。

 -   若脱敏模板匹配类型是**字段名称**，则取**Data**中的**dataHeaderList**进行匹配。
-   若脱敏模板匹配类型是**敏感类型**，则取**Data**中的**ruleList**进行匹配。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~141845~~)。

调用API的请求格式，请参见本文示例中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Data|String|\{"dataHeaderList":\["name","age"\],"dataList":\[\["l\*\*\*",18\],\["l\*\*\*",17\]\],"ruleList":\[1002,null\]\}|脱敏完成后的数据，采用JSON格式的字符串表述。

 脱敏数据包含以下内容：

 -   **dataHeaderList**：表示脱敏数据的列名。
-   **dataList**：表示需要脱敏的数据。字段顺序和脱敏数据的列名一致。
-   **ruleList** : 敏感类型ID。 |
|RequestId|String|813BA9FA-D062-42C4-8CD5-11A7640B96E6|结果的请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ExecDatamask
&Data={"dataHeaderList":["name","age"],"dataList":[["lily",18],["lucy",17]]}
&TemplateId=1
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<ExecDatamaskResponse>
     <Data>{"dataHeaderList":["name","age"],"dataList":[["l***",18],["l***",17]],"ruleList":[1002,null]}</Data>
     <RequestId>813BA9FA-D062-42C4-8CD5-11A7640B96E6</RequestId>
</ExecDatamaskResponse>
```

`JSON`格式

```
{
    "Data": "{\"dataHeaderList\":[\"name\",\"age\"],\"dataList\":[[\"l***\",18],[\"l***\",17]],\"ruleList\":[1002,null]}",
    "RequestId": "813BA9FA-D062-42C4-8CD5-11A7640B96E6"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Sddp)查看更多错误码。

