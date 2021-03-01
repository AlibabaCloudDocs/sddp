# List of operations by function

The following tables list the API operations available for use in Data Security Center \(DSC\).

## Security configuration

|Operation|Description|
|---------|-----------|
|[CreateConfig](/intl.en-US/API Reference/Security configuration/CreateConfig.md)|Modifies a configuration item in the general configuration for anomaly alerts.|
|[ModifyDefaultLevel](/intl.en-US/API Reference/Security configuration/ModifyDefaultLevel.md)|Modifies the risk levels of data, including the default risk level of data that DSC cannot classify as sensitive or insensitive and the risk levels of data that DSC classifies as sensitive.|
|[CreateRule](/intl.en-US/API Reference/Security configuration/CreateRule.md)|Creates a custom sensitive data detection rule.|
|[ModifyDataLimit](/intl.en-US/API Reference/Security configuration/ModifyDataLimit.md)|Modifies configuration items for a data asset that you authorize DSC to access. You can modify only configuration items for ApsaraDB RDS databases. For example, you can change the username or password used to log on to an ApsaraDB RDS database.|
|[ModifyRuleStatus](/intl.en-US/API Reference/Security configuration/ModifyRuleStatus.md)|Enables or disables a sensitive data detection rule in DSC.|
|[ModifyRule](/intl.en-US/API Reference/Security configuration/ModifyRule.md)|Modifies a custom sensitive data detection rule in DSC.|
|[DescribeDataLimits](/intl.en-US/API Reference/Security configuration/DescribeDataLimits.md)|Queries data assets, such as MaxCompute projects, ApsaraDB RDS databases, or Object Storage Service \(OSS\) buckets, that you authorize DSC to access.|
|[DeleteDataLimit](/intl.en-US/API Reference/Security configuration/DeleteDataLimit.md)|Deletes a data asset, such as a MaxCompute project, an ApsaraDB RDS database, or an OSS bucket, that you authorize DSC to access.|
|[DescribeConfigs](/intl.en-US/API Reference/Security configuration/DescribeConfigs.md)|Queries configuration items in the general configuration for anomaly alerts.|
|[DeleteRule](/intl.en-US/API Reference/Security configuration/DeleteRule.md)|Deletes a custom sensitive data detection rule from DSC.|
|[DescribeDataLimitDetail](/intl.en-US/API Reference/Security configuration/DescribeDataLimitDetail.md)|Queries the details of a data asset, such as a MaxCompute project, an ApsaraDB RDS database, or an OSS bucket, that you authorize DSC to access.|
|[DescribeRules](/intl.en-US/API Reference/Security configuration/DescribeRules.md)|Queries sensitive data detection rules in DSC.|

## Sensitive data detection

|Operation|Description|
|---------|-----------|
|[DescribeDataAssets](/intl.en-US/API Reference/Sensitive data detection/DescribeDataAssets.md)|Queries the sensitive data detection results of data assets that you authorize Data Security Center \(DSC\) to access.|
|[DescribeColumns](/intl.en-US/API Reference/Sensitive data detection/DescribeColumns.md)|Queries columns in MaxCompute or ApsaraDB RDS tables that you authorize DSC to access.|
|[DescribeInstances](/intl.en-US/API Reference/Sensitive data detection/DescribeInstances.md)|Queries MaxCompute, ApsaraDB RDS, or OSS instances that you authorize DSC to access.|
|[DescribeTables](/intl.en-US/API Reference/Sensitive data detection/DescribeTables.md)|Queries MaxCompute or ApsaraDB RDS tables that you authorize DSC to access.|
|[DescribeOssObjects](/intl.en-US/API Reference/Sensitive data detection/DescribeOssObjects.md)|Queries OSS objects that you authorize DSC to access.|
|[DescribePackages](/intl.en-US/API Reference/Sensitive data detection/DescribePackages.md)|Queries the information about the MaxCompute packages that you authorize DSC to access. For example, the information may include the names of the MaxCompute packages, accounts of the MaxCompute package owners, and risk levels of the MaxCompute packages.|
|[DescribeOssObjectDetail](/intl.en-US/API Reference/Sensitive data detection/DescribeOssObjectDetail.md)|Queries the details of an OSS object that you authorize DSC to access.|

## Anomalous activity processing

|Operation|Description|
|---------|-----------|
|[ModifyEventTypeStatus](/intl.en-US/API Reference/Anomalous activity processing/ModifyEventTypeStatus.md)|Enables one or more anomalous activity subtypes in DSC.|
|[DescribeEvents](/intl.en-US/API Reference/Anomalous activity processing/DescribeEvents.md)|Queries anomalous activities.|
|[DescribeEventDetail](/intl.en-US/API Reference/Anomalous activity processing/DescribeEventDetail.md)|Queries the details of an anomalous activity, including the time when the anomalous activity occurred, description of the anomalous activity, and status of the anomalous activity.|
|[ModifyEventStatus](/intl.en-US/API Reference/Anomalous activity processing/ModifyEventStatus.md)|Processes an anomalous activity.|
|[DescribeEventTypes](/intl.en-US/API Reference/Anomalous activity processing/DescribeEventTypes.md)|Queries the types of anomalous activities.|

