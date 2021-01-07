# Pay-as-you-go

Sensitive Data Discovery and Protection \(SDDP\) supports the pay-as-you-go billing method. This topic describes how you are billed in pay-as-you-go mode.

## Billable items

You are billed for the following items in SDDP:

-   Sensitive data detection for structured and unstructured data
-   Data de-identification

## Billing cycle

You are billed for your daily usage of SDDP. A pay-as-you-go bill is generated within 3 hours after a billing cycle \(one day\) ends. The bill lists the usage and fee details of that day. You can view the bill information in Billing Management.

-   Sensitive data detection: The bill for a day includes only the charge for the tables and objects for which the scan is completed on that day. If the scan of a table or an object starts on one day but ends on the next day, the charge is included in the bill for the next day. This bill is generated within 3 hours after the next day ends.
-   Data de-identification: The bill for a day includes only the charge for de-identification tasks that are completed on that day.

## Pricing

|Billable item|Data source|Price \(USD\)|Billing unit|
|-------------|-----------|-------------|------------|
|Sensitive data detection|Structured data, which is billed based on the total number of tables: MaxCompute, ApsaraDB RDS, self-managed databasehosted on Elastic Compute Service \(ECS\), DRDS, and PolarDB|0.6|Table|
|Unstructured data, which is billed based on the total size of objects: Object Storage Service \(OSS\)|0.6|GB|
|Data de-identification|ApsaraDB RDS, MaxCompute, and OSS|0.5|100,000 cells|

**Note:**

-   After SDDP is authorized to access your projects, databases, or buckets for the first time, SDDP scans all data in them. The fee of the full scan is calculated.
-   Structured data is rescanned if the schema of the data is changed. The tables whose schema is changed in the related projects or databases are rescanned and the fee of the rescan is calculated.
-   Unstructured data is rescanned if the data is modified. Only the OSS objects that are modified are rescanned and the fee of the rescan is calculated.
-   When you add or modify a custom sensitive data detection rule, a full scan is triggered.
-   The minimum size of scanned data to be charged for each OSS bucket is 0.1 GB. When the size of scanned data in a single OSS bucket is less than 100 MB, the scan fee is calculated based on 0.1 GB.
-   When the system calculates fees, it considers 1 TB as 1,024 GB.

## Example

Assume that a pay-as-you-go user has 180 tables stored in an ApsaraDB RDS database. After SDDP is authorized to access the ApsaraDB RDS database for the first time, SDDP scans all the 180 tables in the database for sensitive data. The fee for the full scan is calculated based on the following equation: 180 × 0.6 = USD 108. On the next day, the schema of six tables in the ApsaraDB RDS database is changed. SDDP rescans the six tables. The fee for the rescan is calculated based on the following equation: 6 × 0.6 = USD 3.6. By the end of the next day, the total fee is calculated based on the following equation: 108 + 3.6 = USD 111.6.

## Overdue payments

Alibaba Cloud has updated the policy for shutting down instances upon overdue payments for all cloud services. In most cases, after the payment for an instance is overdue for 15 days, the instance is shut down.

**Note:** Overdue payments may cause service suspension. The system sends you a notification if you have an overdue payment for an instance. You must renew your instance as early as possible to prevent service suspension.

## References

[Sensitive data scan and detection](/intl.en-US/FAQ/Sensitive data scan and detection.md)

