# ManualTriggerMaskingProcess

You can call this operation to trigger a de-identification task.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Sddp&api=ManualTriggerMaskingProcess&type=RPC&version=2019-01-03)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ManualTriggerMaskingProcess|The operation that you want to perform.

 Set the value to ManualTriggerMaskingProcess. |
|Id|Long|Yes|1|The ID of the de-identification task.

 **Note:** The ID of the de-identification task is a number. You can call the DescribeDataMaskingTasks operation to query the ID. |
|Lang|String|No|zh|The language of the request and response. Valid values:

 -   **zh**: Chinese
-   **en**: English |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|769FB3C1-F4C9-4\*\*\*\*\*\*|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ManualTriggerMaskingProcess
&Id=1
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ManualTriggerMaskingProcessResponse>
  <RequestId>769FB3C1-F4C9-4******</RequestId>
</ManualTriggerMaskingProcessResponse>
```

`JSON` format

```
{
    "RequestId":"769FB3C1-F4C9-4******"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Sddp).

