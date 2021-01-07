# Manage scan tasks

Sensitive Data Discovery and Protection \(SDDP\) automatically creates sensitive data scan tasks for authorized data assets. On the Identify task monitoring page, you can view the details of scan tasks that are created by SDDP for scanning authorized data assets and rerun the scan tasks as required.

SDDP allows you to manage scan tasks that scan your data stored in Object Storage Service \(OSS\), ApsaraDB RDS, DRDS, PolarDB, Tablestore, self-managed databases hosted on Elastic Compute Service \(ECS\) instances, and MaxCompute.

After you authorize SDDP to access specific data assets, SDDP automatically creates and runs scan tasks for these data assets to detect sensitive data. By default, the **automatic scan** feature is enabled for scan tasks that are created by SDDP. This feature allows SDDP to run a full scan on authorized data assets and then scan the data that is newly written to or modified in these data assets at an interval of 4 hours. In addition, after you create or modify a sensitive data detection rule, SDDP automatically reruns scan tasks. SDDP charges you for the size of scanned data. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md).

## View the details of scan tasks

On the Identify task monitoring page, you can view the details of each scan task, such as the related data asset, task status, and time when the task was completed. To view the details of scan tasks, perform the following steps:

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identify task monitoring**.

3.  Click the tab of the service for which you want to view the details of scan tasks.

4.  Select the region, enter the name of the data asset, specify the beginning and end of the time range to query, and then click **Search**.

5.  In the task list, view the details of each scan task, such as the related data asset, task status, and time when the task was completed.


## Rescan your data assets

You can rerun scan tasks in the following scenarios:

-   If you have not enabled the **automatic scan** feature for a scan task, the scan task is not run after it is created. You must rerun the scan task to start it.
-   If you enable the **automatic scan** feature for a scan task, SDDP automatically reruns the scan task to scan the data that is newly written to or modified in the data asset at an interval of 4 hours. You can also rerun the scan task to immediately scan the data asset for sensitive data after you modify the data in the data asset.

**Note:** SDDP charges you daily for the number of files that are scanned. SDDP also charges you for rescans. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md).

To rescan a data asset for sensitive data, perform the following steps:

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identify task monitoring**.

3.  Click the tab of the service for which you want to rescan data.

4.  Find the data asset that you want to rescan and click **Rescan** in the Operation column.

5.  In the **Confirm rescan** message, click **OK**.

    Generally, the rescan can be completed within 10 minutes. Wait until the data asset is scanned.

    After the rescan is started, the scan task enters the **Scanning** or **Waiting** state. The percentage that is displayed in the **Scan Status** column indicates the progress of the scan task. After the rescan is completed, the scan task enters the **Complete** state.

    ![Scanning](../images/p183653.png)


