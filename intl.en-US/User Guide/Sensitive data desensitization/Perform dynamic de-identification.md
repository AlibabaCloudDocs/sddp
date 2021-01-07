# Perform dynamic de-identification

You can call the ExecDatamask operation to dynamically de-identify sensitive data.

You can call the [ExecDatamask](/intl.en-US/API Reference/Sensitive data desensitization/ExecDatamask.md) operation to dynamically de-identify sensitive data. When you call this operation, you must specify the ID of a de-identification template. De-identification templates can be used for both static de-identification and dynamic de-identification. You can view the IDs of de-identification templates on the Desensitization Template page in the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview). You can also create de-identification templates. For more information, see [Manage de-identification templates](/intl.en-US/User Guide/Sensitive data desensitization/Manage de-identification templates.md).

![Desensitization Template page](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9744298951/p130805.png)

## Limits

When you call the ExecDatamask operation to dynamically de-identify sensitive data, the size of the sensitive data that is specified by the `Data` parameter must be less than 2 MB.

## View the call history of the ExecDatamask operation

Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview). Choose **Data desensitization** \> **Dynamic desensitization**. On the Dynamic desensitization page, view the call history of the ExecDatamask operation. Each record includes the name of the API operation, the unique identifier \(UID\) of the Alibaba Cloud account or RAM user that was used to call the API operation, the IP address of the user who initiated the call, the time when the API operation was first and last called, and the total number of calls.

![Dynamic de-identification](../images/p183662.png)

**Note:** Only one record is generated for calls that were initiated by the same account from the same IP address. In this case, the cumulative number of calls is recorded.

