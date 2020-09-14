# Perform static de-identification

Sensitive Data Discovery and Protection \(SDDP\) allows you to create de-identification tasks to de-identify your sensitive data in MaxCompute, Relational Database Service \(RDS\), Object Storage Service \(OSS\), and PolarDB. In this way, you can protect sensitive data in your data assets. This topic describes how to create, query, and view a de-identification task.

SDDP is authorized to access your data assets, such as MaxCompute projects, OSS buckets, and RDS or PolarDB databases. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

Based on de-identification algorithms, SDDP masks, encrypts, or replaces sensitive data detected in authorized data assets and stores de-identified data in the destination location that you specify. In this way, SDDP ensures that sensitive data can be used while it is safely protected. For more information about the de-identification algorithms that SDDP supports, see [Supported de-identification algorithms](/intl.en-US/FAQ/Supported de-identification algorithms.md).

**Note:** SDDP allows you to perform static de-identification on OSS objects, RDS tables, MaxCompute tables, and PolarDB tables.

SDDP supports both static and dynamic de-identification. Compared with static de-identification, dynamic de-identification is more flexible and allows you to de-identify specific sensitive data. The size of sensitive data that can be dynamically de-identified at a time must be less than 2 MB. For more information, see [Perform dynamic de-identification](/intl.en-US/User Guide/Sensitive data desensitization/Perform dynamic de-identification.md).

## Procedure

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Desensitization** \> **Static Desensitization**.

3.  On the Static Desensitization page, click **Add Desensization Task**.

4.  Perform the steps in the wizard to create a custom de-identification task.

    1.  Enter basic task information, including the task name and description, and click **Next**.

        **Note:** You can specify a custom task name.

        ![Basic Task Information step](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7744298951/p51131.png)

    2.  Configure the data to be de-identified and click **Next**. The following tables describe the parameters for configuring the data to be de-identified of different types.

        -   Specify an **RDS, MaxCompute, or PolarDB table** to be de-identified

            ![Specify an RDS, MaxCompute, or PolarDB table to be de-identified](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7744298951/p85903.png)

            |Parameter|Description|
            |---------|-----------|
            |**Types of Data Storage**|The type of the data asset that contains the sensitive data to be de-identified. Set this parameter to **RDS Table / MaxCompute Table / PolarDB Table**.|
            |**Source Product**|The Alibaba Cloud service that contains the sensitive data to be de-identified. Valid values: **RDS**, **MaxCompute**, and **PolarDB**.|
            |**Source Database/Project**|Required. The project or database for storing the table that contains the sensitive data to be de-identified.|
            |**Source Table Name**|Required. The table that contains the sensitive data to be de-identified.|
            |**Source Partition**|Optional. The partition that contains the sensitive data to be de-identified. For more information about how to specify a partition, see [Specify a partition](#section_cjr_9pz_lq0). You can configure partitions when you create a MaxCompute table. Partitions define different logical divisions of a table to help you efficiently query specific content. For more information about partitions, see [Partition](/intl.en-US/Product Introduction/Definitions/Partition.md).

**Note:**

            -   This parameter is available only when you set the **Source Product** parameter to **MaxCompute**.
            -   If you leave this parameter unspecified, SDDP de-identifies sensitive data in all partitions of the table. |
            |**Sample SQL**|Optional. The SQL statement that specifies the data to be de-identified. If you leave this parameter unspecified, SDDP de-identifies all sensitive data in the table. **Note:** This parameter is available only when you set the **Source Product** parameter to **RDS**. |

        -   Upload a local file or specify an **OSS file** to be de-identified

            ![Upload a local file or specify an OSS file to be de-identified](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7744298951/p85988.png)

            |Parameter|Description|
            |---------|-----------|
            |**Types of Data Storage**|The type of the data asset that contains the sensitive data to be de-identified. Set this parameter to **OSS Files**.|
            |**File Source**|The source of the file that contains the sensitive data to be de-identified. Valid values: **Uploaded Local File** and **OSS Bucket**. **Note:** You can upload only a TXT, CSV, XLSX, or XLS file. |
            |**OSS Bucket Where the Source File Is Located**|The OSS bucket for storing the file that contains the sensitive data to be de-identified. You can enter keywords to search for the target OSS bucket.|
            |**Source File Names**|The name of the OSS file that contains the sensitive data to be de-identified. The file name must contain a file name extension. Only TXT, CSV, XLSX, and XLS files are supported. To specify multiple OSS files of the same format at a time, turn on the **Open the Pass** switch.

**Note:** After you turn on the switch, you can use the wildcard \(\*\) to specify multiple OSS files at a time. You can only use the wildcard in the file name prefix, for example, test\*.xls. SDDP will apply the same de-identification rules to all the OSS files that are specified at a time. Make sure that the OSS files share the same schema. |
            |**Source File Description**|The description of the source file. This parameter is required only when you set the **File Source** parameter to **Uploaded Local File**.|
            |**Separator Selection**|Optional. The field delimiter. This parameter is required for CSV and TXT files. Select a field delimiter based on the file format. Valid values:             -   **Semicolon ";" \(MacOS/Linux default\)**
            -   **Comma "," \(Windows default\)** |
            |**Table Contains Header Rows**|Optional. Specifies whether the data to be de-identified includes the table header.|

    3.  Configure the de-identification algorithm and click **Next**.

        In the field list, turn on the **Desensitization** switch for each field that requires de-identification and select a de-identification algorithm as required. For more information about de-identification algorithms, see [Configure de-identification algorithms](/intl.en-US/User Guide/Sensitive data desensitization/Configure de-identification algorithms.md).

        **Note:**

        -   You can click **View and Modify Parameters** next to the selected algorithm to view or modify the rule of the algorithm.
        -   A field is de-identified only after the Desensitization switch is turned on for this field.
        ![Desensitization Algorithm step](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7744298951/p53927.png)

    4.  Specify the destination location for storing the de-identified data. Click **Test** to check whether SDDP can write data to the specified destination location. After the test is passed, click **Next**.

        ![Destination Location Configuration step](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p66209.png)

    5.  Configure the processing logic.

        ![Confirm Process Logic step](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p85687.png)

        |Parameter|Description|
        |---------|-----------|
        |**How the Task Is Triggered**|The mode in which the de-identification task is run. Valid values:         -   **Manual Only**: You must manually run the de-identification task on the Static Desensitization page.
        -   **Scheduled Only**: The de-identification task is automatically run at the specified time on an hourly, daily, or monthly basis.
        -   **Manual + Scheduled**: The de-identification task is automatically run at the specified time on an hourly, daily, weekly, or monthly basis. You can also manually run the de-identification task as required. |
        |**Turn on Incremental Desensitization**|Optional. Specifies whether to enable incremental de-identification. If you turn on this switch, only the data that is added after the last de-identification will be de-identified. You must specify a field whose value is increased over time as the incremental identifier. For example, you can specify the creation time field or the auto-increment ID field as the incremental identifier.**Note:** SDDP only supports incremental de-identification for RDS databases. |
        |**Shard Field**|Optional. The field based on which the system divides the source data to multiple shards and de-identifies them concurrently. In this way, the de-identification efficiency is guaranteed. You can specify one or more shard fields as required.**Note:**

        -   SDDP only supports incremental de-identification for RDS databases. We recommend that you use the primary key or a unique index as the shard field.
        -   By default, the system selects the primary key as the shard field if you do not specify a shard field. You must specify a shard filed if the source data does not have a primary key. Otherwise, the de-identification task fails.
        -   The query performance and data accuracy may deteriorate if you specify excessive shard fields. Exercise caution when you set this parameter. |
        |**Table Name Conflict Resolution**|The handling method if a table exists with the same name as the specified destination table. Valid values:         -   Delete the target table and create a table with the same name
        -   Attach data to the target table: We recommend that you select this option. |
        |**Row Conflict Resolution**|The handling method if conflicting rows exist in the destination table. Valid values:         -   Keep conflicting rows in the target table and discard the new data: We recommend that you select this option.
        -   Delete conflicting rows in the target table and insert the new data |

    6.  Click **Submit**.

        The de-identification task appears on the **Desensitization Task Configuration** tab of the **Static Desensitization** page.

5.  Run the de-identification task.

    Find the de-identification task, turn on the ![Run](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p51363.png) switch, and click **Start** in the Actions column to run the de-identification task.

    ![Run the de-identification task](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p85995.png)

    **Note:** You can modify or delete a de-identification task after it is created. However, a running de-identification task cannot be modified or deleted.

6.  View the running progress and status of the de-identification task.

    After the de-identification task is started, click the **Task Execution Status** tab. On this tab, click **Search** to update the running progress and status of tasks.

    **Note:** If you do not click **Search**, the created de-identification task may not be found on the **Task Execution Status** tab.

    You can check whether the de-identification task is run in the **Status** column. For more information about the failure causes, see [Troubleshooting](#section_eq7_qqb_ahn).

    ![Task running progress and status](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p85999.png)


## Specify a partition

|Partition|Format|Example|
|---------|------|-------|
|N weeks after the specified date|Custom partition field=$\[yyyymmdd+7\*N\]|time=$\[20190710+7\*1\]. It indicates that the data generated in the week after July 10, 2019 is to be de-identified.|
|N weeks before the specified date|Custom partition field=$\[yyyymmdd-7\*N\]|time=$\[20190710-7\*3\]. It indicates that the data generated in the three weeks before July 10, 2019 is to be de-identified.|
|N days after the specified date|Custom partition field=$\[yyyymmdd+N\]|time=$\[20190710+2\]. It indicates that the data generated in the two days after July 10, 2019 is to be de-identified.|
|N days before the specified date|Custom partition field=$\[yyyymmdd-N\]|time=$\[20190710-5\]. It indicates that the data generated in the five days before July 10, 2019 is to be de-identified.|
|N hours after the specified time|Custom partition field=$\[hh24mi:ss+N/24\]|time=$\[0924mi:ss+N/24\]. It indicates that the data generated in the two hours after 09:00 in the 24-hour clock is to be de-identified.|
|N hours before the specified time|Custom partition field=$\[hh24mi:ss-N/24\]|time=$\[0924mi:ss-1/24\]. It indicates that the data generated in the hour before 09:00 in the 24-hour clock is to be de-identified.|
|N minutes after the specified time|Custom partition field=$\[hh24mi:ss+N/24/60\]|time=$\[0924mi:ss+2/24/60\]. It indicates that the data generated in the two minutes after 09:00 in the 24-hour clock is to be de-identified.|
|N minutes before the specified time|Custom partition field=$\[hh24mi:ss-N/24/60\]|time=$\[0924mi:ss-2/24/60\]. It indicates that the data generated in the two minutes before 09:00 in the 24-hour clock is to be de-identified.|

## View the details of and modify de-identification tasks

On the **Static Desensitization** page, you can view the details of de-identification tasks that you have created. In the de-identification task list, click the ID of a de-identification task in the **Task ID** column to view the task details.

![View task details](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p86002.png)

To modify a de-identification task, enter the task ID in the search bar and click **Desensitization Task Search**. The target de-identification task appears. Then, click Modify in the Actions column to modify the de-identification task.

![Modify a de-identification task](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8744298951/p110942.png)

## Troubleshooting

|Error message|Description|
|-------------|-----------|
|The de-identification task does not exist. The task may have been deleted or disabled.|The error message returned because the de-identification task is deleted or disabled. If the switch in the **Actions** column is turned off for the de-identification task, the task is disabled.|
|Incorrect recurrence configuration of the scheduled task.|The error message returned because the time specified for running the de-identification task daily is invalid.|
|The de-identification source instance does not exist.|The error message returned because the instance containing the source table does not exist.|
|The de-identification target instance does not exist.|The error message returned because the instance is deleted or the permission to access the instance is revoked.|
|The de-identification source table does not exist.|The error message returned because the table is deleted or the permission to access the instance that contains the table is revoked.|
|Incorrect de-identification algorithm parameter.|The error message returned because the parameters of the de-identification algorithm are incorrectly configured.|
|Empty source table column.|The error message returned because no data exists in the partition column of the source table.|
|Failed to write data to the target table.|The error message returned because the system fails to write data to the destination table that you specify.|
|Failed to query the source table.|The error message returned because the specified data is not found in the source table.|
|Failed to create the target table.|The error message returned because the destination table does not exist in the specified location.|
|No primary key has been found.|The error message returned because the primary key is missing in the RDS source table. For more information about primary keys, see [How can I view the primary key of an ApsaraDB RDS for MySQL table?](/intl.en-US/FAQs/Databases/How to view the primary key fields of a table in apsaradb for MySQL.md)|
|Incorrect ODPS partition field configured for the task.|The error message returned because the source or destination partition is incorrectly configured when you create the de-identification task.|

