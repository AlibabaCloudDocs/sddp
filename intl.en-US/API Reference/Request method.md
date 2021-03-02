# Request method

To send a Data Security Center \(DSC\) API request, you must send an HTTP GET request to the DSC endpoint. You must add the request parameters that correspond to the API operation being called. After you call the API operation, the system returns a response. All requests and responses are UTF-8 encoded.

## Request syntax

DSC API operations use the remote procedure call \(RPC\) protocol. You can call DSC API operations by sending HTTP GET requests.

Use the following request syntax when you send an API request:

```
https://Endpoint/?Action=xx&Parameters
```

where:

-   Endpoint: the endpoint of DSC is sddp.cn-zhangjiakou.aliyuncs.com.
-   Action: the name of the operation being called. For example, to query the information about the MaxCompute packages that you authorize DSC to access, you must set the Action parameter to DescribePackages.
-   Version: the version number of the API. The version number of the DSC API is 2019-01-03.
-   Parameters: the request parameters for the operation. Separate multiple parameters with ampersands \(&\).

    Request parameters include both common parameters and operation-specific parameters. Common parameters include the information such as the API version number and authentication information. For more information, see [Common parameters](/intl.en-US/API Reference/Common parameters.md).


The following example demonstrates how to call the DescribePackages operation to query the information about the MaxCompute packages that you authorize DSC to access:

**Note:** The following code has been formatted to facilitate reading.

```
http(s)://sddp.cn-zhangjiakou.aliyuncs.com/? Action=DescribePackages
&Format=xml
&Version=2019-01-03
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&TimeStamp=2012-06-01T12:00:00Z
...
```

## Signature method

You must sign all API requests to ensure security. DSC uses the specified request signature to verify the identity of the request sender. Therefore, each API request must contain signature information, regardless of whether it is sent by using HTTP or HTTPS.

DSC implements symmetric encryption by using an AccessKey pair to verify the identity of the request sender. Similar to a logon username and password, an AccessKey pair is an identity credential issued to Alibaba Cloud accounts and RAM users. An AccessKey pair consists of an AccessKey ID and an AccessKey secret. The AccessKey ID is used to verify the identity of the user, whereas the AccessKey secret is used to encrypt and verify the signature string. You must keep your AccessKey secret strictly confidential.

You must add a signature string to a DSC API request in the following format:

```
https://endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
```

The DescribePackages operation is used in the example. Assume that the AccessKey ID is `testid` and the AccessKey secret is `testsecret`. The following code shows the request URL to be signed:

```
https://sddp.cn-zhangjiakou.aliyuncs.com/?Action=DescribePackages
&TimeStamp=2016-02-23T12:46:24Z
&Format=XML
&AccessKeyId=testid
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&Version=2019-01-03
&SignatureVersion=1.0
```

Perform the following steps to calculate the signature string:

1.  Use the request parameters to create a string-to-sign.

    ```
    GET&%2F&AccessKeyId%3Dtestid&Action%3DDescribePackages&Format%3DXML&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&SignatureVersion%3D1.0&TimeStamp%3D2016-02-23T12%253A46%253A24Z&Version%3D2018-12-03
    ```

2.  Calculate the hash-based message authentication code \(HMAC\) value of the string-to-sign.

    Append an ampersand \(&\) to the AccessKey secret as the key to calculate the HMAC value. In this example, the key is `testsecret&`.

    ```
    CT9X0VtwR86fNWSnsc6v8YGOjuE=
    ```

3.  Add the signature string to the request as the Signature parameter.

    ```
    https://sddp.cn-zhangjiakou.aliyuncs.com/?Action=DescribePackages
    &TimeStamp=2016-02-23T12:46:24Z
    &Format=XML
    &AccessKeyId=testid
    &SignatureMethod=HMAC-SHA1
    &SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
    &Version=2019-01-03
    &SignatureVersion=1.0
    &Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D
    ```


**Note:** Alibaba Cloud provides SDKs in multiple languages and third-party SDKs to simplify signature algorithm coding. For more information about Alibaba Cloud SDKs, see [Alibaba Cloud Development Kit \(SDK\)](https://www.alibabacloud.com/zh/support/developer-resources?spm=a2c5t.10695662.1996646101.searchclickresult.7e6c5b4fbkB1Id).

