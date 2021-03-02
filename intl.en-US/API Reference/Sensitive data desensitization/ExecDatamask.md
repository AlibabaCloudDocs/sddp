# ExecDatamask

Dynamically de-identifies sensitive data.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Sddp&api=ExecDatamask&type=RPC&version=2019-01-03)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ExecDatamask|The operation that you want to perform.

 Set the value to **ExecDatamask**. |
|Data|String|Yes|\{"dataHeaderList":\["name","age"\],"dataList":\[\["lily",18\],\["lucy",17\]\]\}|The sensitive data to be de-identified, which is described in a JSON string. The string contains the following parameters:

 -   **dataHeaderList**: the names of columns that contain the sensitive data to be de-identified.
-   **dataList**: the data to be de-identified. The column order of the data to be de-identified is the same as that specified in the dataHeaderList parameter. |
|TemplateId|Long|Yes|1|The ID of the de-identification template. The ID is generated after you create the de-identification template in the [Data Security Center \(DSC\) console](https://yundunnext-pre.console.aliyun.com/?p=sddp&accounttraceid=8c6b3535-f65e-4ef2-a2ac-744be5154805#/overview). Choose **Data desensitization** \> **Desensitization Template** to obtain the ID of the de-identification template. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~141845~~).

For more information about sample requests, see the "Examples" section in this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|String|\{"dataHeaderList":\["name","age"\],"dataList":\[\["l\*\*y",18\],\["l\*\*y",17\]\]\}|The de-identified data, which is described in a JSON string.

 The string contains the following parameters:

 -   **dataHeaderList**: the names of columns that contain the de-identified data.
-   **dataList**: the de-identified data. The column order of the de-identified data is the same as that indicated by the dataHeaderList parameter. |
|RequestId|String|813BA9FA-D062-42C4-8CD5-11A7640B96E6|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ExecDatamask
&Data={"dataHeaderList":["name","age"],"dataList":[["lily",18],["lucy",17]]}
&TemplateId=1
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ExecDatamaskResponse>
      <data>{"dataHeaderList":["name","age"],"dataList":[["l**y",18],["l**y",17]]}</data>
      <RequestId>813BA9FA-D062-42C4-8CD5-11A7640B96E6</RequestId>
</ExecDatamaskResponse>
```

`JSON` format

```
{
    "data": "{\"dataHeaderList\":[\"name\",\"age\"],\"dataList\":[[\"l**y\",18],[\"l**y\",17]]}", 
    "RequestId": "813BA9FA-D062-42C4-8CD5-11A7640B96E6"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Sddp).

