# Data authorization

When you authorize Sensitive Data Discovery and Protection \(SDDP\) to access data in MaxCompute, ApsaraDB RDS, or Object Storage Service \(OSS\), the authorization may fail. This topic describes the possible causes of an authorization failure to help you troubleshoot the failure.

## What are the possible causes for the failure to authorize SDDP to access ApsaraDB RDS?

-   The username or password for accessing the RDS database is invalid.
-   The service IP addresses of SDDP are deleted from the whitelist of the RDS database.
-   The RDS database resides in the classic network, but the public endpoint of the RDS database is inaccessible due to access control.

## What are the possible causes for the failure to authorize SDDP to access MaxCompute?

-   The name of the MaxCompute project is invalid.
-   The SDDP account fails to be added to the MaxCompute project.

## References

[Grant access to data assets](/intl.en-US/User Guide/Grant access to data assets.md)

