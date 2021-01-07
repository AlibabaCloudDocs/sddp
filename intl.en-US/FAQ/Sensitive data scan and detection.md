# Sensitive data scan and detection

This topic provides answers to commonly asked questions about sensitive data scan and detection.

-   [What types of data assets can SDDP scan?](#section_fen_4pj_lwg)
-   [How long does it take to scan data in my data asset after I authorize SDDP to access the data asset?](#section_hv1_nu2_vqi)
-   [How does SDDP scan data in an unstructured data asset, such as an OSS bucket?](#section_7np_ggx_mab)
-   [Can SDDP rescan an OSS object after the object is scanned?](#section_let_6i8_6qf)
-   [How does SDDP scan data in a structured data asset, such as a MaxCompute project or an ApsaraDB RDS database?](#section_uxo_wqg_q6j)
-   [Does SDDP log on to a database to obtain data?](#section_8ut_oez_69d)
-   [When will a rescan be triggered?](#section_9lh_qg8_epu)
-   [Will SDDP skip my data in a scan?](#section_n7c_p51_g1q)

## What types of data assets can SDDP scan?

SDDP can scan data assets that store structured data or unstructured data. SDDP can scan the following types of data assets:

-   ApsaraDB RDS databases and self-managed databases, which store structured data
-   MaxCompute projects, which store structured data
-   Object Storage Service \(OSS\) buckets, which store unstructured data

## How long does it take to scan data in my data asset after I authorize SDDP to access the data asset?

SDDP starts to scan your data asset within 2 hours after it is authorized to access the data asset. The time taken to scan your data depends on the data volume. If a data asset contains a large number of tables, for example, more than 10,000 tables, it takes a long period of time to scan the data asset. If the total size of objects stored in an OSS bucket is large, for example, more than 1 PB, it also takes a long period of time to scan the OSS bucket. When SDDP scans your data, the scan results are progressively updated on the **Overview** page in the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview). For more information, see [View summary information](/intl.en-US/User Guide/View summary information.md).

## How does SDDP scan data in an unstructured data asset, such as an OSS bucket?

SDDP scans data that is stored in an unstructured data asset and determines whether the objects are sensitive.

-   **First scan**: After you authorize SDDP to access an OSS bucket, SDDP scans all objects that are stored in the OSS bucket.
-   **Scan of incremental data**: If you add objects to or modify objects stored in the OSS bucket, SDDP scans the new or modified objects.

## Can SDDP rescan an OSS object after the object is scanned?

If the object remains unchanged, SDDP does not rescan it. If you modify the object, SDDP rescans the object within 4 to 8 hours after the modification.

## How does SDDP scan data in a structured data asset, such as a MaxCompute project or an ApsaraDB RDS database?

SDDP scans the names and values of fields in databases or projects, and determines whether the fields are sensitive. For example, SDDP scans the name and values of the age field. If SDDP cannot determine whether a field is sensitive based only on the values of the field, SDDP also checks the name of the field to determine whether the field is sensitive.

-   **First scan**: After you authorize SDDP to access a database or project, SDDP scans all tables in the database or project.
-   **Scan of incremental data**: If you add tables to the database or project, SDDP scans the new tables. If you modify the schema of an existing table by changing fields, SDDP rescans the table.

## Does SDDP log on to a database to obtain data?

If authorized, SDDP logs on to a database and samples data to detect sensitive data. SDDP does not save data from databases or MaxCompute projects.

## When will a rescan be triggered?

SDDP automatically rescans data in an authorized data asset in the scenarios described in the following table.

|Scenario|Scan logic|Billing|
|--------|----------|-------|
|You authorize SDDP to access your data asset for the first time.|SDDP scans all data in the data asset.|SDDP charges you for a full scan on data in the data asset.|
|You modify data in a data asset after SDDP has scanned the data asset with authorization.|If you add fields to or delete fields from a MaxCompute or database table, SDDP automatically rescans the table. If you add rows to or delete rows from a table, SDDP does not automatically rescan the table.|SDDP charges you for a full scan on data in the data asset.|
|If you add objects to or modify objects stored in an OSS bucket, SDDP automatically scans the new or modified objects. **Note:** If you only delete objects from an OSS bucket, SDDP does not automatically rescan the bucket.

|SDDP charges you for scanning the new or modified objects.|
|You change sensitive data detection rules. For example, you create, delete, enable, or disable rules.|SDDP automatically scans all data in all authorized data assets.|SDDP charges you for a full scan on data in all authorized data assets.|

## Will SDDP skip my data in a scan?

SDDP does not scan an OSS object if its size reaches 200 MB. SDDP scans only OSS objects whose size is less than 200 MB.

**Note:** A package is considered as a single object. If the total size of all files in a package reaches 200 MB, SDDP does not scan the package.

