# Perform static de-identification

Data Security Center \(DSC\) can de-identify and protect sensitive data in your data assets. This topic describes how to create and query de-identification tasks.

DSC is authorized to access your data assets, such as MaxCompute projects, Object Storage Service \(OSS\) buckets, and ApsaraDB RDS databases. For more information about access authorization, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

Based on de-identification algorithms, DSC redacts, encrypts, or substitutes sensitive data detected in authorized data assets and stores de-identified data in the location that you specify. This way, DSC ensures that sensitive data can be used while it is safely protected. For more information about the de-identification algorithms that are supported by DSC, see [Supported data de-identification algorithms](/intl.en-US/FAQ/Supported data de-identification algorithms.md).

**Note:** DSC allows you to perform static de-identification on OSS objects, ApsaraDB RDS tables, MaxCompute tables, PolarDB tables, and OceanBase tables.

DSC supports both static and dynamic de-identification. Compared with static de-identification, dynamic de-identification is more flexible and allows you to de-identify specified sensitive data. The size of sensitive data that can be dynamically de-identified at a time must be less than 2 MB. For more information about dynamic de-identification, see [Perform dynamic de-identification](/intl.en-US/User Guide/Data desensitization/Perform dynamic de-identification.md).

## Create a de-identification task

1.  Log on to the [DSC console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Data desensitization** \> **Static Desensitization**.

3.  On the Static Desensitization page, click **Add Desensitization Task**.

4.  Perform the steps in the wizard to create a custom de-identification task.

    1.  Enter basic task information and click **Next**.

        **Note:** You can specify a custom task name.

    2.  Specify the data to be de-identified and click **Next**. The following tables describe the parameters for specifying the data to be de-identified of different types.

        -   Specify an **ApsaraDB RDS, MaxCompute, or PolarDB table** to be de-identified

            ![Specify an ApsaraDB RDS or MaxCompute table to be de-identified](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7744298951/p85903.png)

            |Parameter|Description|
            |---------|-----------|
            |**Types of data storage**|The type of the data asset that contains the sensitive data to be de-identified. Set this parameter to **RDS table/DRDS table/MaxCompute table/PolarDB table/OceanBase table/ADB-MySQL table**.|
            |**Source Product**|The Alibaba Cloud service that contains the sensitive data to be de-identified. Valid values: **RDS**, **MaxCompute**, and **PolarDB**.|
            |**Source Database/Project**|Required. The project or database for storing the table that contains the sensitive data to be de-identified.|
            |**Source table name**|Required. The table that contains the sensitive data to be de-identified.|
            |**Source Partition**|Optional. The partition that contains the sensitive data to be de-identified. For more information about how to specify a partition, see [Specify a partition](#section_cjr_9pz_lq0). You can configure partitions when you create a MaxCompute table. Partitions define different logical divisions of a table to help you efficiently query specific content. For more information, see [Partition](/intl.en-US/Product Introduction/Definitions/Partition.md).

**Note:**

            -   If you set the **Source Product** parameter to RDS or PolarDB, you do not need to set the **Source Partition** parameter.
            -   If you leave the **Source Partition** parameter unspecified, DSC de-identifies sensitive data in all partitions of the table. |
            |**Sample SQL**|Optional. The SQL statement that specifies the data to be de-identified. If you leave this parameter unspecified, DSC de-identifies all sensitive data in the table. **Note:** If you set the **Source Product** parameter to MaxCompute or PolarDB, you do not need to set the **Sample SQL** parameter. |

        -   Specify an **OSS object** to be de-identified

            |Parameter|Description|
            |---------|-----------|
            |**Types of data storage**|The type of the data asset that contains the sensitive data to be de-identified. Set this parameter to **OSS files**.|
            |**File source**|The source of the file that contains the sensitive data to be de-identified. Valid values: **Uploaded Local File** and **OSS Bucket**. **Note:** You can upload only a TXT, CSV, XLSX, or XLS file. |
            |**OSS Bucket where the source file is located**|The OSS bucket where the source file resides. You can enter keywords to search for the OSS bucket where the source file resides.|
            |**Source file names**|The name of the source file. The file name must contain a file name extension. Only TXT, CSV, XLSX, and XLS files are supported. To specify multiple source files in the same format at a time, turn on **Open the pass**.

**Note:** After you turn on the switch, you can use the wildcard \(\*\) to specify multiple source files at a time. You can use the wildcard only in the file name prefix, for example, test\*.xls. DSC applies the same de-identification rules to all the source files that are specified at a time. Make sure that the source files share the same schema. |
            |**Source file description**|The description of the source file. If you set the **File source** parameter to **OSS Bucket**, you do not need to set this parameter.|
            |**Separator selection**|Optional. The field delimiter. This parameter is required for CSV and TXT files. Select a field delimiter based on the file format. Valid values:             -   **Semicolon ";" \(MacOS/Linux default\)**
            -   **Comma "," \(Windows default\)** |
            |**Table contains header rows**|Optional. Specifies whether the data to be de-identified includes the table header.|

    3.  Configure the de-identification algorithm and click **Next**.

        In the field list, turn on **Desensitization** for each field that requires de-identification and select a de-identification algorithm as required. For more information about de-identification algorithms, see [Configure de-identification algorithms](/intl.en-US/User Guide/Data desensitization/Configure de-identification algorithms.md).

        **Note:**

        -   You can click **View and Modify Parameters** next to the selected algorithm to view or modify the rule of the algorithm.
        -   A field is de-identified only after Desensitization is turned on for this field.
    4.  Specify the location for storing the de-identified data. Click **Test** to check whether DSC can write data to the specified location. After the test is passed, click **Next**.

    5.  Configure the processing logic.

        ![Confirm Process Logic](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8744298951/p85687.png)

        |Parameter|Description|
        |---------|-----------|
        |**How the task is triggered**|The mode in which the de-identification task is run. Valid values:         -   **Manual Only**: You must manually run the de-identification task on the Static Desensitization page.
        -   **Scheduled Only**: The de-identification task is automatically run at the specified time on an hourly, daily, weekly, or monthly basis.
        -   **Manual + Scheduled**: The de-identification task is automatically run at the specified time on an hourly, daily, weekly, or monthly basis. You can also manually run the de-identification task as required. |
        |**Turn on incremental desensitization**|Optional. Specifies whether to enable incremental de-identification. If you turn on this switch, only the data that is added after the last de-identification task is complete will be de-identified. You must specify a field whose value is increased over time as the incremental identifier. For example, you can specify the creation time field or the auto-increment ID field as the incremental identifier.**Note:** DSC supports incremental de-identification only for ApsaraDB RDS databases. |
        |**Shard field**|Optional. The field based on which DSC divides the source data to multiple shards and concurrently de-identifies them. This improves the de-identification efficiency. You can specify one or more shard fields as required.**Note:**

        -   DSC supports incremental de-identification only for ApsaraDB RDS databases. We recommend that you use the primary key or a unique index as the shard field.
        -   If you do not specify a shard field, DSC uses the primary key as the shard field by default to de-identify the source data. You must specify a shard field if the source data does not have a primary key. Otherwise, the de-identification task fails.
        -   The query performance and data accuracy may deteriorate if you specify excessive shard fields. Exercise caution when you set this parameter. |
        |**Table name conflict resolution**|The solution used if the specified destination table exists. Valid values:         -   Delete the target table and create a table with the same name
        -   Attach data to the target table: We recommend that you select this option. |
        |**Row Conflict Resolution**|The solution used if conflicting rows exist in the destination table. Valid values:         -   Keep conflicting rows in the target table and discard the new data: We recommend that you select this option.
        -   Delete conflicting rows in the target table and insert the new data |

    6.  Click **Submit**.

        The de-identification task appears on the **Desensitization task configuration** tab of the **Static Desensitization** page.

5.  Run the de-identification task.

    After the de-identification task is created, find the de-identification task, turn on the ![Run](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8744298951/p51363.png) switch, and then click **Start** in the Actions column to run the de-identification task.

    ![Successful de-identification](../images/p183659.png)

    **Note:** DSC allows you to modify or delete a de-identification task after it is created. However, a running de-identification task cannot be modified or deleted.

6.  View the progress and status of the de-identification task.

    After the de-identification task is started, click the **Task Execution Status** tab. On the **Task Execution Status** tab, click **Search** to update the progress and status of tasks.

    **Note:** If you do not click **Search**, the created de-identification task may not be displayed on the **Task Execution Status** tab.

    You can check whether the de-identification task is run in the **Status** column. For more information about the failure causes, see [Troubleshoot failures to run de-identification tasks](#section_eq7_qqb_ahn).

    ![Task progress and status](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8744298951/p85999.png)


## Specify a partition

|Partition|Format|Example|
|---------|------|-------|
|N weeks after the specified date|Custom partition field=$\[yyyymmdd+7\*N\]|time=$\[20190710+7\*1\]. It indicates that the data generated in the week after July 10, 2019 is to be de-identified.|
|N weeks before the specified date|Custom partition field=$\[yyyymmdd-7\*N\]|time=$\[20190710-7\*3\]. It indicates that the data generated in the three weeks before July 10, 2019 is to be de-identified.|
|N days after the specified date|Custom partition field=$\[yyyymmdd+N\]|time=$\[20190710+2\]. It indicates that the data generated in the two days after July 10, 2019 is to be de-identified.|
|N days before the specified date|Custom partition field=$\[yyyymmdd-N\]|time=$\[20190710-5\]. It indicates that the data generated in the five days before July 10, 2019 is to be de-identified.|
|N hours after the specified time|Custom partition field=$\[hh24mi:ss+N/24\]|time=$\[0924mi:ss+2/24\]. It indicates that the data generated in the two hours after 09:00:00 in the 24-hour clock is to be de-identified.|
|N hours before the specified time|Custom partition field=$\[hh24mi:ss-N/24\]|time=$\[0924mi:ss-1/24\]. It indicates that the data generated in the hour before 09:00:00 in the 24-hour clock is to be de-identified.|
|N minutes after the specified time|Custom partition field=$\[hh24mi:ss+N/24/60\]|time=$\[0924mi:ss+2/24/60\]. It indicates that the data generated in the two minutes after 09:00:00 in the 24-hour clock is to be de-identified.|
|N minutes before the specified time|Custom partition field=$\[hh24mi:ss-N/24/60\]|time=$\[0924mi:ss-2/24/60\]. It indicates that the data generated in the two minutes before 09:00:00 in the 24-hour clock is to be de-identified.|

## Query de-identification tasks

On the **Static Desensitization** page, you can view the details of de-identification tasks that you have created. In the task list, click the ID of a de-identification task in the **Task ID** column to view the task details.

![View task details](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8744298951/p86002.png)

To modify a de-identification task that has been created, enter the ID of the task in the search box and click **Desensitization Task Search**. The de-identification task appears. Then, click Modify in the Actions column to modify the de-identification task.

![Modify a de-identification task](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8744298951/p110942.png)

## Troubleshoot failures to run de-identification tasks

|Error message|Description|
|-------------|-----------|
|The desensitization task does not exist. The task may have been deleted or closed.|The error message returned because the de-identification task is deleted or disabled. If the switch in the **Actions** column is turned off for the de-identification task, the task is disabled.|
|Incorrect recurrence configuration of the scheduled task.|The error message returned because the time specified for running the de-identification task daily is invalid.|
|The desensitization source instance does not exist.|The error message returned because the instance that contains the source table does not exist.|
|The desensitization target instance does not exist.|The error message returned because the instance is deleted or the permissions to access the instance are revoked.|
|The desensitization source table does not exist.|The error message returned because the table is deleted or the permissions to access the instance that contains the table are revoked.|
|Incorrect desensitization algorithm parameter.|The error message returned because the parameters of the de-identification algorithm are incorrectly configured.|
|Empty source table list.|The error message returned because no data exists in the partition column of the source table.|
|Failed to write data to the target table.|The error message returned because DSC fails to write data to the destination table that you specify.|
|Failed to query the source table.|The error message returned because the specified data is not found in the source table.|
|Failed to create the target table.|The error message returned because the destination table does not exist in the specified location.|
|No primary key has been found.|The error message returned because the primary key is missing in the ApsaraDB RDS source table. For more information about primary keys, see [How can I view the primary key of an ApsaraDB RDS for MySQL table?](/intl.en-US/FAQs/Databases/How to view the primary key fields of a table in apsaradb for MySQL.md)|
|Incorrect ODPS partition field configured for the task.|The error message returned because the source or destination partition is incorrectly configured when you create the de-identification task.|

