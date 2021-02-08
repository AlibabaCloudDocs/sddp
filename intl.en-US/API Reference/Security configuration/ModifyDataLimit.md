# ModifyDataLimit

You can call this operation to modify configuration items for a data asset that you authorize Sensitive Data Discovery and Protection \(SDDP\) to access.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Sddp&api=ModifyDataLimit&type=RPC&version=2019-01-03)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyDataLimit|The operation that you want to perform.

 Set the value to ModifyDataLimit. |
|Id|Long|Yes|11|The unique ID of the data asset for which you want to modify configuration items.

 **Note:** You can call the **DescribeDataLimits** operation to query the ID of the data asset. |
|ResourceType|Integer|Yes|1|The type of the service to which the data asset belongs. Valid values:

 -   1: MaxCompute
-   2: Object Storage Service \(OSS\)
-   5: Relational Database Service \(RDS\) |
|Lang|String|No|zh|The language of the request and response. Valid values:

 -   **zh**: Chinese
-   **en**: English |
|ServiceRegionId|String|No|cn-hangzhou|The region ID of the data asset.

 Valid values:

 -   cn-beijing: China \(Beijing\)
-   cn-zhangjiakou: China \(Zhangjiakou\)
-   cn-huhehaote: China \(Hohhot\)
-   cn-hangzhou: China \(Hangzhou\)
-   cn-shanghai: China \(Shanghai\)
-   cn-shenzhen: China \(Shenzhen\)
-   cn-hongkong: Hong Kong |
|UserName|String|No|tstst|The username for logging on to the RDS database that you authorize SDDP to access. |
|Password|String|No|\*\*\*|The password for logging on to the RDS database that you authorize SDDP to access. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|7C3AC882-E5A8-4855-BE77-B6837B695EF1|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyDataLimit
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyDataLimitResponse>
  <RequestId>7C3AC882-E5A8-4855-BE77-B6837B695EF1</RequestId>
</ModifyDataLimitResponse>
```

`JSON` format

```
{
	"RequestId":"7C3AC882-E5A8-4855-BE77-B6837B695EF1"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Sddp).

