# Authorize DSC to access Alibaba Cloud resources

Before you use Data Security Center \(DSC\), you must authorize DSC to access Alibaba Cloud resources. This topic describes how to authorize DSC to access Alibaba Cloud resources.

DSC is activated.

When you log on to the DSC console for the first time after you activate DSC, the Overview page prompts you to authorize DSC to access Alibaba Cloud resources. DSC can access Alibaba Cloud services, such as Object Storage Service \(OSS\), ApsaraDB RDS, and MaxCompute, scan your data assets for sensitive data, and analyze the detected sensitive data only after the authorization is complete.

## Procedure

1.  Log on to the [DSC console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  On the Overview page, click **Authorize Now**.

    After you click Authorize Now, Alibaba Cloud automatically creates the AliyunServiceRoleForDSC role for DSC. You can view the created service-linked role on the RAM Roles page of the [Resource Access Management \(RAM\) console](https://ram.console.aliyun.com/roles). You can also query the information about the service-linked role for DSC by using the API or command line interface \(CLI\). For more information, see [Service-linked roles](/intl.en-US/RAM Role Management/Service-linked roles.md).

    After you authorize DSC to access Alibaba Cloud resources, you must authorize DSC to access specific data assets before DSC can scan the data assets for sensitive data and analyze the detected sensitive data. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).


## Service-linked role for DSC

Role name: AliyunServiceRoleForDSC

Policy name: AliyunServiceRolePolicyForDSC

## Delete the service-linked role

If you no longer need to use DSC, you can delete the service-linked role for DSC. You can delete the AliyunServiceRoleForDSC role in the [RAM console](https://ram.console.aliyun.com/roles). For more information, see [Service-linked roles](/intl.en-US/RAM Role Management/Service-linked roles.md).

## Usage notes

Do not confuse the operation of authorizing DSC to access Alibaba Cloud resources with the operation of authorizing DSC to access data assets. The former operation authorizes DSC to access other data services of Alibaba Cloud, whereas the latter operation authorizes DSC to access specific data assets in these data services. After you authorize DSC to access Alibaba Cloud resources, you must authorize DSC to access specific data assets before DSC can scan the data assets for sensitive data and analyze the detected sensitive data. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

