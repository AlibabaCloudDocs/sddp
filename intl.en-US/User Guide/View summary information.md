# View summary information

After you activate Data Security Center \(DSC\) and configure risk levels and sensitive data detection rules, you can view the summary information on the Overview page of the DSC console. The summary information includes statistics on authorized data assets, sensitive data detection, static de-identification, and anomalous activities.

DSC can detect sensitive data in MaxCompute, ApsaraDB RDS, Object Storage Service \(OSS\), Tablestore, self-managed databases hosted on Elastic Compute Service \(ECS\) instances, DRDS, and PolarDB.

**Note:** For your data security and privacy, DSC performs only necessary operations such as sensitive data detection and static de-identification. DSC does not store your data.

## View statistics on authorized data assets

In the **Data asset authorization** section, you can view statistics on authorized data assets, such as the proportion of data assets that DSC is authorized to access in all your data assets. For each service, this section displays the total number of data assets, the number of data assets that DSC is authorized to access, and the number of unauthorized data assets. This section also displays the total number of times that DSC scans data assets, and the number of objects or tables that DSC scanned.

Click **Authorize Now** for a service. The Cloud hosting page appears, where you can authorize DSC to access more data assets and view, edit, or delete authorized data assets. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

![Authorize Now](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p96927.png)

## View the service usage in pay-as-you-go mode

In the **Billed consumption** section, you can view the size of structured data scanned, unstructured data scanned, and data de-identified by DSC. You can click the tabs to view the data scanned or de-identified on the current day, in the current week, in the current month, and in the current year.

**Note:**

-   Structured data refers to data stored in MaxCompute, ApsaraDB RDS, OSS, Tablestore, self-managed databases hosted on ECS instances, DRDS, and PolarDB. Unstructured data refers to data stored in OSS.
-   The billing unit for de-identification is cell.
-   The statistics in this section may not be updated in real time. We recommend that you use the statistics only for reference and check your bills for actual service usage.

![Current status](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p65136.png)

Click **Billing details** to go to the Bills page in User Center, where you can view the details of each bill.

## View statistics on sensitive data detection

In the **Data Identification Result** section, you can view the numbers of sensitive tables, fields, and objects detected in authorized data assets.

![Sensitive data detection result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p43398.png)

DSC detects sensitive data based on the sensitive data detection rules that you have configured. Sensitive data detection rules include built-in rules and custom rules. DSC detects sensitive tables, fields, and objects and classifies them by risk level based on the sensitive data detection rules. For more information, see [Manage detection rules](/intl.en-US/User Guide/Sensitive data discovery/Manage detection rules.md).

The Data Identification Result section displays the following statistics:

-   **Sensitive Tables**: the total number of sensitive tables detected in MaxCompute, ApsaraDB RDS, Tablestore, self-managed databases hosted on ECS instances, DRDS, and PolarDB.
-   **Sensitive Fields**: the total number of sensitive fields detected in MaxCompute, ApsaraDB RDS, Tablestore, self-managed databases hosted on ECS instances, DRDS, and PolarDB.
-   **Sensitive Files**: the total number of sensitive objects detected in OSS.
-   **Risk Level Distribution of Sensitive Tables** and **Risk Level Distribution of Sensitive Fields**: the number of sensitive tables or fields at each risk level in the authorized data assets.

    DSC allows you to define the risk levels of sensitive fields in sensitive data detection rules. DSC supports the following risk levels: S1, S2, and S3. The severity of each risk level sequentially increases in the following way:

    -   **S1**: low risk.
    -   **S2**: medium risk.
    -   **S3**: high risk.

## View statistics on static de-identification

In the **Static Desensitization Result** section, you can view the number of sensitive tables that DSC de-identifies by using de-identification algorithms, number of de-identified tables, and number of de-identified fields. You can also view the proportion of tables for which static de-identification is configured in all sensitive tables.

DSC allows you to create static de-identification tasks to de-identify and protect sensitive data in your data assets. For more information, see [Perform static de-identification](/intl.en-US/User Guide/Data desensitization/Perform static de-identification.md).

![Static de-identification result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p65163.png)

## View statistics on and trends in anomalous activities

In the **Anomalous Event Summary** section, you can view the trends in anomalous activities detected in the last seven days, one month, six months, or twelve months.

![Anomalous Event Summary](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6644298951/p51102.png)

The Anomalous Event Summary section displays the following statistics:

-   **Unprocessed Anomalous Events**: the number of anomalous activities that have not been processed.

    DSC can detect anomalous activities that occurred in reading and using sensitive data. Such activities include anomalous permission access, anomalous data flows, and anomalous data operations. DSC detects anomalous activities and generates anomaly alerts based on the anomaly alert configuration.

-   **Processed Anomalous Events**: the number of anomalous activities that have been processed.

    DSC allows you to process an anomalous activity by confirming it as a violation or excluding it as a false positive.


## Query data assets

Click **Data Asset Search** in the upper-right corner of the Overview page. Then, query data assets that contain sensitive data and the risk levels of sensitive data detected by DSC.

You can set the following filters to query data assets:

-   **Risk Levels**: Select one or more risk levels of sensitive data to query data assets. If you do not select a risk level, DSC queries data assets that contain sensitive data at all risk levels.

    **Note:** The **N/A** option indicates an unknown risk level.

-   **Asset Scope**: Select one or more types of data assets to query, such as MaxCompute project and MaxCompute table.
-   **With Sensitive Data**: Select a sensitive data type from the drop-down list to query data assets.

    **Note:** Each option maps a sensitive data detection rule, which can be a built-in rule or a custom rule. You can choose **Sensitive data discovery** \> **Identification Rules** in the left-side navigation pane to view the rules.

-   **Asset Name**: Enter the name of a project, instance, database, package, table, or object to query the specific data asset.

