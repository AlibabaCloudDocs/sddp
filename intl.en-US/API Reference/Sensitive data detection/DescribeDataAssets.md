# DescribeDataAssets

Queries the sensitive data detection results of data assets that you authorize Data Security Center \(DSC\) to access.

****

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Sddp&api=DescribeDataAssets&type=RPC&version=2019-01-03)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDataAssets|The operation that you want to perform.

 Set the value to **DescribeDataAssets**. |
|Lang|String|No|zh|The language of the request and response. Default value: **zh**. Valid values:

 -   **zh**: Chinese
-   **en**: English |
|Name|String|No|test|The keyword used to search for data assets. Fuzzy search is supported. |
|RiskLevels|String|No|S1|The risk level of the data asset. Separate multiple risk levels with commas \(,\). Valid values:

 -   **S1**: low risk level
-   **S2**: medium risk level
-   **S3**: high risk level
-   **S4**: highest risk level |
|RuleId|Long|No|11122200|The unique ID of the sensitive data detection rule that the data asset hits.

 **Note:** If you query sensitive data detection results based on the sensitive data detection rule that the data assets hit, you can call the [DescribeRules](~~141389~~) operation to query the ID of the sensitive data detection rule. |
|RangeId|Integer|No|1|The type of the data asset. Valid values:

 -   **1**: MaxCompute project
-   **2**: MaxCompute table
-   **3**: MaxCompute package
-   **11**: AnalyticDB for MySQL database
-   **12**: AnalyticDB for MySQL table
-   **21**: Object Storage Service \(OSS\) bucket
-   **22**: OSS object
-   **31**: Tablestore instance
-   **32**: Tablestore table
-   **51**: ApsaraDB RDS database
-   **52**: ApsaraDB RDS table
-   **61**: self-managed database hosted on an Elastic Compute Service \(ECS\) instance
-   **62**: self-managed table hosted on an ECS instance
-   **71**: DRDS database
-   **72**: DRDS table
-   **81**: PolarDB database
-   **82**: PolarDB table
-   **91**: AnalyticDB for PostgreSQL database
-   **92**: AnalyticDB for PostgreSQL table |
|PageSize|Integer|No|20|The number of entries to return on each page. By default, the number of entries on each page is 20. If you do not set the PageSize parameter, 20 entries are returned per page by default.

 **Note:** We recommend that you do not leave the PageSize parameter empty. |
|CurrentPage|Integer|No|1|The number of the page to return. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~141847~~).

For more information about sample requests, see the "Examples" section in this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CurrentPage|Integer|1|The page number of the returned page. |
|Items|Array of Asset| |The data assets that were queried. |
|Acl|String|private|The access control list \(ACL\) that controls the access permissions of the OSS bucket. |
|CreationTime|Long|1536751124000|The time when the data asset was created. Unit: milliseconds. |
|DataType|String|OSS\_BUCKET|The data type of the data asset. |
|Id|String|268|The unique ID of the data asset. |
|Labelsec|Integer|0|The security status of the MaxCompute data asset. |
|Name|String|gxdata|The name of the data asset that was queried. |
|ObjectKey|String|Internal|The key value of the OSS object. |
|OdpsRiskLevelName|String|S4|The risk level of the MaxCompute data asset. Valid values:

 -   **S1**: low risk level
-   **S2**: medium risk level
-   **S3**: high risk level
-   **S4**: highest risk level |
|Owner|String|dtdep-239-\*\*\*\*\*\*|The Alibaba Cloud account that owns the data asset. |
|ProductCode|String|RDS|The code of the service to which the data asset belongs. Valid values:

 -   MaxCompute
-   OSS
-   RDS |
|ProductId|String|5|The ID of the service to which the data asset belongs. |
|Protection|Boolean|false|Indicates whether the MaxCompute data asset is being protected. |
|RiskLevelId|Long|2|The risk level ID of the data asset. |
|RiskLevelName|String|Medium risk level|The risk level of the data asset. |
|RuleName|String|\*\*\* rule|The name of the sensitive data detection rule that the data asset hits. |
|Sensitive|Boolean|true|Indicates whether the data asset contains sensitive data. Valid values:

 -   **true**: The data asset contains sensitive data.
-   **false**: The data asset does not contain sensitive data. |
|SensitiveCount|Integer|24|The total number of sensitive data objects in the data assets that were queried. For example, the value can be the total number of sensitive MaxCompute projects, packages, or tables, the total number of sensitive ApsaraDB RDS databases or tables, or the total number of sensitive OSS buckets or objects. |
|SensitiveRatio|String|45%|The percentage of sensitive data in the data assets that were queried. |
|TotalCount|Integer|432|The total number of data objects in the data assets that were queried. For example, the value can be the total number of MaxCompute projects, packages, or tables, the total number of RDS databases or tables, or the total number of OSS buckets or objects. |
|PageSize|Integer|20|The number of entries returned per page. |
|RequestId|String|71064826-726F-4ADA-B879-05D8055476FB|The ID of the request. |
|TotalCount|Integer|1|The total number of queried data assets that contain sensitive data. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDataAssets
&RangeId=1
&<Common request parameters>
```

Sample success responses

`XML` format

```
Response<? xml version="1.0" encoding="UTF-8" ? >
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
		<RiskLevelName>Medium risk level</RiskLevelName>
		<DepartName>***DemoCenter</DepartName>
		<Name>gxdata</Name>
		<Labelsec>0</Labelsec>
		<CreationTime>1536751124000</CreationTime>
		<Sensitive>true</Sensitive>
		<Id>268</Id>
		<Protection>false</Protection>
		<RuleName>*** rule</RuleName>
		<ObjectKey>Internal</ObjectKey>
	</Items>
</DescribeDataAssetsResponse>
```

`JSON` format

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
            "RiskLevelName":"Medium risk level", 
            "DepartName":"***DemoCenter", 
            "Name":"gxdata", 
            "Labelsec":0,
            "CreationTime":1536751124000, 
            "Sensitive":true, 
            "Id":268, 
            "Protection":false, 
            "RuleName":"*** rule",
            "ObjectKey":"Internal",
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Sddp).

