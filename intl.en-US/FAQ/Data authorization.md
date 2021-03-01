# Data authorization

When you authorize Data Security Center \(DSC\) to access data in MaxCompute, ApsaraDB RDS, or Object Storage Service \(OSS\), the authorization may fail. This topic describes the possible causes of an authorization failure to help you troubleshoot the failure.

## What are the possible causes for the failure to authorize DSC to access ApsaraDB RDS?

-   The username or password for accessing the ApsaraDB RDS database is invalid.
-   The service IP addresses of DSC are deleted from the whitelist of the ApsaraDB RDS database.
-   The ApsaraDB RDS database resides on the classic network, but the public endpoint of the ApsaraDB RDS database is inaccessible due to access control.

## What are the possible causes for the failure to authorize DSC to access MaxCompute?

-   The name of the MaxCompute project is invalid.
-   The DSC account fails to be added to the MaxCompute project.

## References

[Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md)

