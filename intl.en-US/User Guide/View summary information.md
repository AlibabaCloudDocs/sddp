# View summary information

After you activate Sensitive Data Discovery and Protection \(SDDP\) and configure risks levels and sensitive data detection rules, SDDP automatically scans your data assets for sensitive data. On the Overview page of the SDDP console, you can view the current status of SDDP and statistics on authorized data assets, sensitive data detection, static desensitization, and anomalous events.

SDDP can scan your data assets for sensitive data. The data assets that SDDP supports include MaxCompute projects, Relational Database Service \(RDS\) databases, Object Storage Service \(OSS\) buckets, Tablestore instances, user-created databases hosted on Elastic Compute Service \(ECS\) instances, PolarDB-X databases, and PolarDB databases.

**Note:** For your data security and privacy, SDDP performs only necessary operations such as sensitive data detection and static de-identification to protect your sensitive data. SDDP does not store any of your data.

## View statistics on authorized data assets

In the **Data Protection Authorization** section, you can view statistics on authorized data assets, including the proportion of authorized data assets in all your data assets. For each service, this section displays the total number of data assets, the number of authorized data assets, the number of unauthorized data assets, the number of times that data assets are scanned, and the number of scanned objects or tables.

Click **Authorize Now** for a service. The Cloud Hosting page appears, where you can authorize SDDP to access more data assets and view, edit, or delete authorized data assets. For more information, see [Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md).

![Authorize SDDP](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6644298951/p96927.png)

## View the service usage in the pay-as-you-go mode

In the **Billed Consumption** section, you can view the size of structured data scanned, unstructured data scanned, and data de-identified by SDDP. You can click the tabs to view the data scanned or de-identified on the current day, in the last seven days, in the current month, and in the current year.

**Note:**

-   Structured data refers to data stored in MaxCompute, RDS, OSS, Tablestore, user-created databases hosted on ECS instances, PolarDB-X, and PolarDB. Unstructured data refers to data stored in OSS.
-   The billing unit for static de-identification is cell.
-   The statistics in this section may not be updated in a timely manner. We recommend that you use the statistics for reference only and check your bills for actual service usage.

![Billed consumption](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6644298951/p65136.png)

You can click **Billing Details** to go to the Bills page in User Center, where you can view the details of each bill.

## View statistics on sensitive data detection

In the **Data Identification Result** section, you can view the numbers of sensitive tables, fields, and objects detected in authorized data assets.

![Sensitive data detection result](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6644298951/p43398.png)

SDDP detects sensitive tables, fields, and objects based on the sensitive data detection rules that you have configured. SDDP provides various built-in rules for sensitive data detection, and also allows you to configure custom detection rules. SDDP automatically detects sensitive tables, fields, and objects and marks them with different risk levels based on sensitive data detection rules. For more information, see [Manage detection rules](/intl.en-US/User Guide/Detect sensitive data/Manage detection rules.md).

The Data Identification Result section displays the following statistics:

-   **Sensitive Tables**: the total number of sensitive tables detected in MaxCompute, RDS, Tablestore, user-created databases hosted on ECS instances, PolarDB-X, and PolarDB.
-   **Sensitive Fields**: the total number of sensitive fields detected in MaxCompute, RDS, Tablestore, user-created databases hosted on ECS instances, PolarDB-X, and PolarDB.
-   **Sensitive Files**: the total number of sensitive objects detected in OSS.
-   **Risk Level Distribution of Sensitive Tables** and **Risk Level Distribution of Sensitive Fields**: the number of sensitive tables or fields at each risk level in the authorized data assets.

    SDDP allows you to define the risk levels of sensitive fields in sensitive data detection rules. SDDP supports the following risk levels: S1, S2, and S3. The severity of each risk level increases sequentially in the following way:

    -   **S1**: low.
    -   **S2**: medium.
    -   **S3**: high.

## View statistics on static de-identification

In the **Static Desensitization Result** section, you can view the numbers of sensitive tables, de-identified tables, and de-identified fields in your data assets. You can also view the proportion of tables for which static de-identification is configured in all sensitive tables.

SDDP allows you to create static de-identification tasks to de-identify and protect sensitive data in your data assets. For more information, see [Perform static de-identification](/intl.en-US/User Guide/Sensitive data desensitization/Perform static de-identification.md).

![Static de-identification result](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6644298951/p65163.png)

## View statistics on and trends in anomalous events

In the **Anomalous Event Summary** section, you can view statistics on anomalous events detected in the last seven days, one month, six months, or twelve months.

![Anomalous event summary](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6644298951/p51102.png)

The Anomalous Event Summary section displays the following statistics:

-   **Unprocessed Anomalous Events**: the number of anomalous events that have not been processed.

    SDDP can detect anomalous events that occurred in reading and using sensitive data, including anomalous permission access, anomalous data flows, and anomalous data operations. SDDP detects anomalous events and generates anomaly alerts based on the anomaly alert configuration.

-   **Processed Anomalous Events**: the number of anomalous events that have been processed.

    SDDP allows you to process an anomalous event by confirming it as a violation or excluding it as a false positive.


## Query data assets

SDDP allows you to query data assets. To query data assets, click **Data Asset Search** in the upper-right corner of the Overview page. On the page that appears, you can query data assets with sensitive data and the risk levels of sensitive data detected by SDDP.

![Query data assets](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7644298951/p51110.png)

SDDP supports the following filters:

-   **Risk Levels**: Specify one or more risk levels of sensitive data to query data assets. If you do not select any risk level, SDDP queries data assets with sensitive data at all risk levels.

    **Note:** The **N/A** option indicates an unknown risk level.

-   **Asset Scope**: Specify one or more types of data assets to query, such as MaxCompute project and MaxCompute table.
-   **With Sensitive Data**: Specify a sensitive data type to query data assets.

    **Note:** Each option maps a sensitive data detection rule, which can be a built-in rule or a custom rule. You can view the rules on the **Sensitive Data Identification** \> **Identification Rules** page.

-   **Asset Name**: Enter the name of a project, instance, database, package, table, or object to query the specific data asset.

