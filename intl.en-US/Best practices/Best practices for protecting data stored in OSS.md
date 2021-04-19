# Best practices for protecting data stored in OSS

This topic shows you how to use Data Security Center \(DSC\) to detect, classify, and protect sensitive data that is stored in Object Storage Service \(OSS\).

Sensitive data includes personal privacy information, passwords, keys, and images that contain sensitive content. Such data is of high value and is stored in your OSS buckets in different formats. The leaks of sensitive data can cause serious economic and brand losses to your enterprise.

After you authorize DSC to access an OSS bucket, DSC detects sensitive data in the OSS bucket, classifies and displays the sensitive data, and tracks the use of the sensitive data. In addition, DSC protects and audits the sensitive data based on predefined security rules, so that you can obtain the security status of your data assets in OSS at any time.

## Scenarios

-   **Sensitive data detection**

    You store a large amount of data in OSS. You cannot determine whether data stored in OSS contains sensitive data and where the sensitive data is stored.

    DSC scans data that is stored in OSS for sensitive data and classifies the sensitive data based on built-in or custom rules. Then, you can use OSS features such as access control and encryption to protect the sensitive data.

-   **Data de-identification**

    If you share data for analysis or use without de-identifying sensitive data, the sensitive data may be leaked.

    DSC supports built-in and custom de-identification algorithms. You can use these algorithms to de-identify sensitive data that is obtained from the production environment before you transfer the sensitive data to other environments such as the development or test environment. DSC ensures that the de-identified sensitive data is usable in other environments.


## Benefits

-   **Visualized**: DSC visualizes the results of sensitive data detection. This allows you to obtain a clear view of the security status of your data assets.
    -   Monitors data access and provides audit logs for you to trace anomalous activities, which reduces security risks to your data.
    -   Increases the overall security transparency of your data assets and enhances data governance.
    -   Reduces the cost of maintaining data security and provides fundamental data for you to formulate security rules that are suitable for your enterprise.
-   **Intelligent**: DSC uses big data technologies, machine learning capabilities, and intelligent algorithms to detect and monitor sensitive data, high-risk activities such as anomalous data access, and potential data leaks. In addition, DSC provides suggestions on how to resolve detected issues.
    -   Allows you to customize the rules to detect sensitive data so that you can ensure that the sensitive data is more accurately and efficiently detected and protected.
    -   Integrates complex data formats and content to a unified data risk model and presents data in a standard manner for you to protect your key data assets.
-   **Cloud-native**: DSC fully leverages its advantages as a cloud-native service and integrates with a variety of data assets on Alibaba Cloud.

    Compared with traditional sensitive data protection software, DSC provides a more robust service architecture and higher availability in a cost-efficient manner, and features higher system security.


## Usage notes

You can activate DSC in pay-as-you-go mode for free. After you authorize DSC to access specific OSS buckets, DSC charges you at a price of USD 0.6 per GB for scanning objects that are stored in the OSS buckets.

DSC scans all data that is stored in your OSS buckets at the first scan and charges you for a full scan. If you add new objects to or modify objects in your OSS buckets after the first scan, DSC charges you only for scanning the new or modified objects. This greatly reduces the expense.

## Procedure

1.  Activate Data Security Center \(DSC\).

2.  Log on to the [DSC console](https://yundun.console.aliyun.com/?p=sddp#/overview).

3.  In the left-side navigation pane, choose **Data asset authorization** \> **Data asset authorization**.

4.  On the OSS tab, click **Unauthorized** and select multiple OSS buckets to authorize DSC to access these OSS buckets at a time.

    You can also find an OSS bucket and click **Authorization** in the Open protection column to authorize DSC to access the OSS bucket. For more information, see [Authorize DSC to access OSS buckets](/intl.en-US/User Guide/Grant access to data assets.md).

    DSC starts to scan objects that are stored in your OSS buckets within 2 hours after the authorization. The time taken to scan objects in your OSS buckets depends on the total size of the objects. For more information, see the "How long does it take to scan data in my data asset after I authorize SDDP to access the data asset?" section of the [Sensitive data scan and detection](/intl.en-US/FAQ/Sensitive data scan and detection.md) topic.

    When DSC scans data, the scan results are progressively updated on the Overview page in the DSC console. For more information, see [View summary information](/intl.en-US/User Guide/View summary information.md).

5.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Sensitive data assets**. On the **OSS** tab, view the results of scanning OSS for sensitive data. For more information, see [View sensitive data detected in OSS](/intl.en-US/User Guide/Sensitive data discovery/View sensitive data.md). In addition, you must handle sensitive objects and risk activities based on the scan results at the earliest opportunity to prevent data security risks.

    We recommend that you perform the following operations:

    1.  Check the number of sensitive objects at each risk level in an OSS bucket that has a high risk level at the earliest opportunity. In addition, check the detection rules that are most frequently hit at each risk level and the number of objects that hit each rule.
    2.  Click **File details** to view the information about the sensitive objects, such as the names, types, and sizes. Check whether the objects have data security risks.
    3.  On the **Original log** page, find the sensitive objects based on their names and view the operations that were performed on the sensitive objects from clients. If necessary, record the IP addresses of the clients from which the operations were performed and check whether suspicious users exist.
    4.  On the **Abnormal event alerts** page, view the anomalous activities based on the risk level and check whether high-risk activities exist.
    5.  De-identify sensitive data. For more information, see [Perform static de-identification](/intl.en-US/User Guide/Data desensitization/Perform static de-identification.md) and [Perform dynamic de-identification](/intl.en-US/User Guide/Data desensitization/Perform dynamic de-identification.md).
    6.  In the [OSS console](https://oss.console.aliyun.com/overview), modify the read and write permissions on the risky OSS buckets or objects. For more information, see [Modify bucket ACLs](/intl.en-US/Console User Guide/Manage buckets/Access control/Modify bucket ACLs.md) and [Configure ACL for objects](/intl.en-US/Console User Guide/Upload, download, and manage objects/Configure ACL for objects.md).

        **Note:** You can configure server-side encryption to encrypt an object when you upload the object to OSS. This helps you prevent leaks of sensitive data. For more information, see [Configure server-side encryption](/intl.en-US/Console User Guide/Manage buckets/Basic settings/Configure server-side encryption.md).


## References

[Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md)

[Overview](/intl.en-US/FAQ/Overview.md)

