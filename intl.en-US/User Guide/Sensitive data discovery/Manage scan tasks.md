# Manage scan tasks

Data Security Center \(DSC\) automatically scans the authorized data assets for sensitive data. On the Identify task monitoring page, you can view the details of scan tasks that are created by DSC to scan authorized data assets and rerun the scan tasks as required.

DSC allows you to manage scan tasks that scan your data stored in Object Storage Service \(OSS\), ApsaraDB RDS, DRDS, PolarDB, Tablestore, self-managed databases hosted on Elastic Compute Service \(ECS\) instances, and MaxCompute.

After you authorize DSC to access specific data assets, DSC automatically creates and runs scan tasks for these data assets to detect sensitive data. By default, the **automatic scan** feature is enabled for scan tasks that are created by DSC. This feature allows DSC to run a full scan on authorized data assets and then scan the data that is newly written to or modified in these data assets at intervals of 4 hours. In addition, after you create or modify a sensitive data detection rule, DSC automatically reruns scan tasks. DSC charges you based on the size of scanned data. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md).

## View the details of scan tasks

On the Identify task monitoring page, you can view the details of each scan task, such as the related data asset, task status, and time when the task was complete. To view the details of scan tasks, perform the following steps:

1.  Log on to the [DSC console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identify task monitoring**.

3.  Click the tab of the service for which you want to view the details of scan tasks.

4.  Select the region, enter the name of the data asset, specify the beginning and end of the time range to query, and then click **Search**.

5.  In the task list, view the details of each scan task, such as the related data asset, task status, and time when the task was complete.


## Rescan your data assets

You can rerun scan tasks in the following scenarios:

-   If you have not enabled the **automatic scan** feature for a scan task, the scan task is not run after it is created. You must rerun the scan task to start it.
-   If you enable the **automatic scan** feature for a scan task, DSC automatically reruns the scan task to scan the data that is newly written to or modified in the data asset at intervals of 4 hours. You can also rerun the scan task to scan the data asset for sensitive data immediately after you modify the data in the data asset.

**Note:** DSC charges you daily for the number of files that are scanned. DSC also charges you for rescans. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md).

To rescan a data asset for sensitive data, perform the following steps:

1.  Log on to the [DSC console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identify task monitoring**.

3.  Click the tab of the service for which you want to rescan data.

4.  Find the data asset that you want to rescan and click **Rescan** in the Operation column.

5.  In the **Confirm rescan** message, click **OK**.

    Generally, the rescan can be complete within 10 minutes. Wait until the data asset is scanned.

    After the rescan is started, the scan task enters the **Scanning** or **Waiting** state. The percentage that is displayed in the **Scan Status** column indicates the progress of the scan task. After the rescan is complete, the scan task enters the **Complete** state.

    ![Scanning](../images/p183653.png)


