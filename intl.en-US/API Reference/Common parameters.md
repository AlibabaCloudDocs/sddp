# Common parameters

This topic describes the common parameters for API operations provided by Data Security Center \(DSC\).

## Common request parameters

Common request parameters must be included in all DSC API requests.

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Format|string|No|The format in which to return the response. Valid values: JSON and XML. Default value: JSON. |
|Version|String|Yes|The version number of the API. Specify the version number in the YYYY-MM-DD format. Set the value to 2019-01-03. |
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request.|
|SignatureMethod|String|Yes|The encryption method of the signature string. Set the value to HMAC-SHA1. |
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the `YYYY-MM-DDThh:mm:ssZ` format. The time must be in UTC. Example: `2013-01-10T12:00:00Z`, which indicates 20:00:00 on January 10, 2013, UTC+8. |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to 1.0.|
|SignatureNonce|String|Yes|A unique, random number used to prevent replay attacks. You must use different numbers for different requests. |
|ResourceOwnerAccount|String|No|The Alibaba Cloud account that owns the resource to be accessed by the API request.|

**Examples**

```
https://sddp.cn-zhangjiakou.aliyuncs.com/
? Format=xml
&Version=2019-01-03
&Signature=Pc5WB8gokVn0xfeu%2FZV%2BiNM1dgI%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2012-06-01T12:00:00Z
```

## Common response parameters

API responses use the HTTP response format where a 2XX status code indicates a successful call and a 4XX or 5XX status code indicates a failed call.

Responses can be returned in the JSON or XML format. You can specify the response format in the request. The default response format is JSON.

Every response returns a unique RequestId value regardless of whether the call is successful.

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!--Result root node-->
        <Operation name+Response>
            <!--Return request tag-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!--Return result data-->
        </Operation name+Response>
                        
    ```

-   JSON format

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*Return result data*/
        }
    ```


