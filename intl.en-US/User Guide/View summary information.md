# View summary information

After you activate Sensitive Data Discovery and Protection \(SDDP\) and configure risk levels and sensitive data detection rules, you can view the summary information on the Overview page of the SDDP console. The summary information includes statistics on authorized data assets, sensitive data detection, static de-identification, and anomalous activities.

SDDP can detect sensitive data in MaxCompute, ApsaraDB RDS, Object Storage Service \(OSS\), Tablestore, self-managed databases hosted on Elastic Compute Service \(ECS\) instances, DRDS, and PolarDB.

**Note:** For your data security and privacy, SDDP performs only necessary operations such as sensitive data detection and static de-identification. SDDP does not store your data.

## View statistics on authorized data assets

In the **Data asset authorization** section, you can view statistics on authorized data assets, such as the proportion of data assets that SDDP is authorized to access in all your data assets. For each service, this section displays the total number of data assets, the number of data assets that SDDP is authorized to access, and the number of unauthorized data assets. This section also displays the total number of times that SDDP scans data assets, and the number of objects or tables that SDDP scanned.

Click **Authorize Now** for a service. The Cloud hosting page appears, where you can authorize SDDP to access more data assets and view, edit, or delete authorized data assets. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

![Authorize Now](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p96927.png)

## View the service usage in pay-as-you-go mode

In the **Billed consumption** section, you can view the size of structured data scanned, unstructured data scanned, and data de-identified by SDDP. You can click the tabs to view the data scanned or de-identified on the current day, in the current week, in the current month, and in the current year.

**Note:**

-   Structured data refers to data stored in MaxCompute, ApsaraDB RDS, OSS, Tablestore, self-managed databases hosted on ECS instances, DRDS, and PolarDB. Unstructured data refers to data stored in OSS.
-   The billing unit for de-identification is cell.
-   The statistics in this section may not be updated in real time. We recommend that you use the statistics only for reference and check your bills for actual service usage.

![Current status](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p65136.png)

Click **Billing details** to go to the Bills page in User Center, where you can view the details of each bill.

## View statistics on sensitive data detection

In the **Data Identification Result** section, you can view the numbers of sensitive tables, fields, and objects detected in authorized data assets.

![Sensitive data detection result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p43398.png)

SDDP detects sensitive data based on the sensitive data detection rules that you have configured. Sensitive data detection rules include built-in rules and custom rules. SDDP detects sensitive tables, fields, and objects and classifies them by risk level based on the sensitive data detection rules. For more information, see [Manage detection rules](/intl.en-US/User Guide/Detect sensitive data/Manage detection rules.md).

The Data Identification Result section displays the following statistics:

-   **Sensitive Tables**: the total number of sensitive tables detected in MaxCompute, ApsaraDB RDS, Tablestore, self-managed databases hosted on ECS instances, DRDS, and PolarDB.
-   **Sensitive Fields**: the total number of sensitive fields detected in MaxCompute, ApsaraDB RDS, Tablestore, self-managed databases hosted on ECS instances, DRDS, and PolarDB.
-   **Sensitive Files**: the total number of sensitive objects detected in OSS.
-   **Risk Level Distribution of Sensitive Tables** and **Risk Level Distribution of Sensitive Fields**: the number of sensitive tables or fields at each risk level in the authorized data assets.

    SDDP allows you to define the risk levels of sensitive fields in sensitive data detection rules. SDDP supports the following risk levels: S1, S2, and S3. The severity of each risk level increases sequentially in the following way:

    -   **S1**: low risk.
    -   **S2**: medium risk.
    -   **S3**: high risk.

## View statistics on static de-identification

In the **Static Desensitization Result** section, you can view the numbers of sensitive tables that SDDP de-identifies by using de-identification algorithms, de-identified tables, and de-identified fields. You can also view the proportion of tables for which static de-identification is configured in all sensitive tables.

SDDP allows you to create static de-identification tasks to de-identify and protect sensitive data in your data assets. For more information, see [Perform static de-identification](/intl.en-US/User Guide/Sensitive data desensitization/Perform static de-identification.md).

![Static de-identification result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p65163.png)

## View statistics on and trends in anomalous activities

In the **Anomalous Event Summary** section, you can view the trends in anomalous activities detected in the last seven days, one month, six months, or twelve months.

![Anomalous Event Summary](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p51102.png)

The Anomalous Event Summary section displays the following statistics:

-   **Unprocessed Anomalous Events**: the number of anomalous activities that have not been processed.

    SDDP can detect anomalous activities that occurred in reading and using sensitive data, which include anomalous permission access, anomalous data flows, and anomalous data operations. SDDP detects anomalous activities and generates anomaly alerts based on the anomaly alert configuration.

-   **Processed Anomalous Events**: the number of anomalous activities that have been processed.

    SDDP allows you to process an anomalous activity by confirming it as a violation or excluding it as a false positive.


## Query data assets

Click **Data Asset Search** in the upper-right corner of the Overview page. Then, query data assets with sensitive data and the risk levels of sensitive data detected by SDDP.

You can set the following filters to query data assets:

-   **Risk Levels**: Select one or more risk levels of sensitive data to query data assets. If you do not select a risk level, SDDP queries data assets with sensitive data at all risk levels.

    **Note:** The **N/A** option indicates an unknown risk level.

-   **Asset Scope**: Select one or more types of data assets to query, such as MaxCompute project and MaxCompute table.
-   **With Sensitive Data**: Select a sensitive data type from the drop-down list to query data assets.

    **Note:** Each option maps a sensitive data detection rule, which can be a built-in rule or a custom rule. You can choose **Sensitive data discovery** \> **Identification Rules** to view the rules.

-   **Asset Name**: Enter the name of a project, instance, database, package, table, or object to query the specific data asset.

