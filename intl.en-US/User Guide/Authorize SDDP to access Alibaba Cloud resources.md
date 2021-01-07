# Authorize SDDP to access Alibaba Cloud resources

Before you use Sensitive Data Discovery and Protection \(SDDP\), you must authorize SDDP to access Alibaba Cloud resources. This topic shows you how to authorize SDDP to access Alibaba Cloud resources.

SDDP is activated.

When you log on to the SDDP console for the first time after you activate SDDP, the Overview page prompts you to authorize SDDP to access Alibaba Cloud resources. SDDP can access Alibaba Cloud services, such as Object Storage Service \(OSS\), ApsaraDB RDS, and MaxCompute, scan your data assets for sensitive data, and analyze the detected sensitive data only after the authorization is completed.

## Procedure

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  On the Overview page, click **Authorize Now**.

    After you click Authorize Now, Alibaba Cloud automatically creates the AliyunServiceRoleForSDDP role for SDDP. You can view the created service-linked role on the RAM Roles page of the [Resource Access Management \(RAM\) console](https://ram.console.aliyun.com/roles). You can also retrieve a list of service-linked roles for SDDP by using the API or command-line interface \(CLI\). For more information, see [Service-linked roles](/intl.en-US/RAM Role Management/Service-linked roles.md).

    After you authorize SDDP to access Alibaba Cloud resources, you must authorize SDDP to access specific data assets before SDDP can scan the data assets for sensitive data and analyze the detected sensitive data. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).


## Service-linked role for SDDP

Role name: AliyunServiceRoleForSDDP

Policy name: AliyunServiceRolePolicyForSDDP

## Delete a service-linked role

If you no longer need to use SDDP, you can delete the service-linked role for SDDP. You can delete the AliyunServiceRoleForSDDP role in the [RAM console](https://ram.console.aliyun.com/roles). For more information, see [Service-linked roles](/intl.en-US/RAM Role Management/Service-linked roles.md).

## Usage notes

Do not confuse the operation of authorizing SDDP to access Alibaba Cloud resources with the operation of authorizing SDDP to access data assets. The former operation authorizes SDDP to access other data services of Alibaba Cloud, whereas the latter operation authorizes SDDP to access specific data assets in these data services. After you authorize SDDP to access Alibaba Cloud resources, you must authorize SDDP to access specific data assets before SDDP can scan the data assets for sensitive data and analyze the detected sensitive data. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

