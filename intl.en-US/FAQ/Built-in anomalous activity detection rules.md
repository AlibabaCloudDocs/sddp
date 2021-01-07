# Built-in anomalous activity detection rules

This topic describes the built-in anomalous activity detection rules that are supported by Sensitive Data Discovery and Protection \(SDDP\).

|Model type|Model name|Anomaly description|Supported service|
|----------|----------|-------------------|-----------------|
|Anomalous data flow|Sensitive data download in an unusual location|An external attacker obtains the logon credentials of an account and uses the account to download sensitive data.|Object Storage Service \(OSS\), ApsaraDB RDS, and MaxCompute|
|Sensitive data download on an unusual terminal|An external attacker obtains the logon credentials of an account and uses the account to download sensitive data, or an employee downloads sensitive data to a personal terminal.|OSS|
|Sensitive data download during an unusual period|An external attacker obtains the logon credentials of an account and uses the account to download sensitive data, or an employee downloads sensitive data after working hours.|OSS, ApsaraDB RDS, and MaxCompute|
|Sensitive data download for the first time|An account is mistakenly granted the permission to download sensitive data.|OSS, ApsaraDB RDS, and MaxCompute|
|Anomalous volume of downloaded sensitive data|An external attacker obtains the logon credentials of an account and uses the account to download sensitive data, or an employee maliciously backs up sensitive data.|OSS, ApsaraDB RDS, and MaxCompute|
|Download of unnecessary sensitive tables|An account is mistakenly granted the permission to download sensitive data.|ApsaraDB RDS and MaxCompute|
|Unusual low log output|The log feature encounters a failure. As a result, anomalous data operations cannot be effectively detected.|OSS, ApsaraDB RDS, and MaxCompute|
|Anomalous volume of downloaded objects|An external attacker obtains the logon credentials of an account and uses the account to download sensitive data, or an employee maliciously backs up sensitive data.|OSS|
|Anomalous volume of downloaded data|An external attacker obtains the logon credentials of an account and uses the account to download sensitive data, or an employee maliciously backs up sensitive data.|ApsaraDB RDS and MaxCompute|
|Anomalous permission access|Unusual logon time|An external attacker obtains the logon credentials of an account and uses the account to log on to the service, or an employee logs on to the service after working hours.|OSS, ApsaraDB RDS, and MaxCompute|
|Unusual logon terminal|An external attacker obtains the logon credentials of an account and uses the account to log on to the service, or an employee logs on to the service on a personal terminal.|OSS, ApsaraDB RDS, and MaxCompute|
|Unusual logon location|An external attacker obtains the logon credentials of an account and uses the account to log on to the service.|OSS, ApsaraDB RDS, and MaxCompute|
|Download of sensitive objects from an unusual OSS bucket|An account is mistakenly granted the permission to download sensitive data.|OSS|
|No protection for a sensitive MaxCompute project|Protection is disabled for a sensitive MaxCompute project. As a result, the MaxCompute project is not protected when data flows out of it. For more information, see [Project data protection](/intl.en-US/Management/Configure security features/Project data protection.md).|MaxCompute|
|LabelSecurity disabled for a sensitive MaxCompute project|LabelSecurity is disabled for a sensitive MaxCompute project. As a result, the workspace administrator cannot control the access of users to sensitive data in the MaxCompute project. For more information, see [Column-level access control](/intl.en-US/Management/Configure security features/Column-level access control.md).|MaxCompute|
|Sensitive OSS bucket at the security level of public|The security level of a sensitive OSS bucket is set to public. As a result, external users can access sensitive data in the OSS bucket by calling an API operation.|OSS|
|Beyond the maximum idle period for a permission|An unnecessary permission is granted, which violates the principle of minimum authorization. It is difficult to detect external attackers who have obtained such permissions.|OSS, ApsaraDB RDS, and MaxCompute|
|Access to an object that does not exist for multiple times|An external attacker repeatedly makes access attempts.|OSS|
|Access to an unauthorized object for multiple times|An external attacker repeatedly makes access attempts.|OSS|
|Multiple failed access attempts|An external attacker repeatedly makes access attempts.|OSS, ApsaraDB RDS, and MaxCompute|
|Anomalous data operation|Anomalously low risk level marked for a MaxCompute project|The risk level marked for a MaxCompute project is maliciously lowered. As a result, permission control loses effectiveness and data security protection cannot cover all sensitive data.|MaxCompute|
|Sensitive field modification in the SDDP console|An employee maliciously modifies sensitive fields in the SDDP console. Data modification through applications is more risky than data modification in the SDDP console.|MaxCompute|

