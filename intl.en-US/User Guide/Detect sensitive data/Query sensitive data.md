# Query sensitive data

The Sensitive data search page displays all the sensitive data that has been detected in your data assets. You can specify one or more types of sensitive data to query and view the distribution of the queried sensitive data across your data assets.

## Procedure

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Sensitive data search**.

3.  On the Sensitive data search page, set filters as required.

    You can set the following filters:

    -   **Hit data**: the type of sensitive data. You can select multiple types at a time, such as email address and mobile number.
    -   **Enter file name to search/Enter table name to search**: the name of the object or table with sensitive data detected. Fuzzy match is supported.
    -   **Region**: the region where the data asset resides.
    -   **Bucket/Instance/Project**: the name of the bucket, database, instance, or project with sensitive data detected.
    -   Time range: the beginning and end of the time range to query.
    **Note:** If you set multiple filters, SDDP displays the sensitive data that meets all the specified filters.

4.  Click **Search**.


## Related operations

-   **Query sensitive data by risk level**

    On the **OSS-file** tab, set the **Sensitivity level** parameter to S1, S2, or S3 to query sensitive data at the specified risk level.

-   **Sort sensitive data based on the total number of rows or sensitive fields in ascending or descending order**

    On a specific tab such as the **RDS-table** tab, click the ![Sort icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2744298951/p112154.png) icon to the right of **Total number of rows** or **Sensitive column** to sort sensitive data based on the total number of rows or sensitive fields in ascending or descending order. The data is sorted in descending order after you click the icon for the first time, and is sorted in ascending order the next time you click the icon.

-   **View the details of sensitive data**

    Find the specific data asset and click **Details** or **Column details** in the Operation column. The **Hit query** panel appears if the data asset is an Object Storage Service \(OSS\) bucket, and the **Column details** panel appears if the data asset is a table. In the Hit query or Column details panel, you can view the following information about the sensitive data detected in the data asset:

    -   **Column name**: the name of the sensitive field detected in the table.

        **Note:** This parameter is displayed only in the **Column details** panel for a table in an ApsaraDB RDS database, MaxCompute project, self-managed database hosted on an Elastic Compute Service \(ECS\) instance, DRDS database, PolarDB database, or Tablestore instance. The **Hit query** panel for an OSS object does not display this parameter.

    -   **Hit Rules**: the type and name of the sensitive data detection rule that is hit.
    -   **Sensitivity level**: the risk level of the detected sensitive data.
    -   **Number of hits**: the number of times that the sensitive data detection rule is hit in the object.

        **Note:** This parameter is displayed only in the **Hit query** panel for an OSS object.

    -   **Data sampling**: the sensitive fields detected by SDDP. You can specify the number of samples to be collected by setting the **Sensitive data sampling** parameter on the **Cloud hosting** page. You can set this parameter to 0, 5, or 10. Then, SDDP displays the collected samples based on your setting.

