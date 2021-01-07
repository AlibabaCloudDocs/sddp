# Supported data de-identification algorithms

This topic describes the data de-identification algorithms that are supported by Sensitive Data Discovery and Protection \(SDDP\).

|Category|Description|Algorithm|Input|Applicable sensitive data and scenario|
|--------|-----------|---------|-----|--------------------------------------|
|Hashing|The algorithms are irreversible. This type of algorithms is applicable to password protection or the scenario where you must check whether data is sensitive by comparison.

You can use common hash algorithms and set the salt value.

|MD5|Salt value|-   Sensitive data: key information
-   Scenario: data storage |
|Secure Hash Algorithm 1 \(SHA-1\)|Salt value|
|SHA-256|Salt value|
|Hash-based Message Authentication Code \(HMAC\)|Salt value|
|Redaction by using asterisks \(\*\) or number signs \(\#\)|The algorithms are irreversible. This type of algorithms is applicable to the scenario where sensitive data is to be shown on the user interface or is to be shared with others.

This type of algorithms masks specified text in sensitive data with asterisks \(\*\) or number signs \(\#\).

|Keeps the first N characters and the last M characters|Values of N and M|-   Sensitive data: sensitive personal information
-   Scenarios:
    -   Data usage
    -   Data sharing |
|Keeps characters from the Xth position to the Yth position|Values of X and Y|
|Masks the first N characters and the last M characters|Values of N and M|
|Masks characters from the Xth position to the Yth position|Values of X and Y|
|Masks characters before a special character when the special character appears for the first time|At sign \(@\), ampersand \(&\), or period \(.\)|
|Masks characters after a special character when the special character appears for the first time|At sign \(@\), ampersand \(&\), or period \(.\)|
|Substitution, which supports customization|Some of the algorithms are reversible. This type of algorithms can be used to de-identify fields in fixed formats, such as ID card numbers.

This type of algorithms substitutes the entire value or a part of the value of a field with the mapped value by using a mapping table or randomly based on a random interval. The substitution based on a mapping table is reversible, whereas the substitution based on a random interval is irreversible. SDDP provides multiple built-in mapping tables and allows you to customize substitution algorithms.

|Substitutes specified content in ID card numbers with mapped values|Mapping table for substituting administrative region IDs|-   Sensitive data:
    -   Sensitive personal information
    -   Sensitive enterprise information
    -   Sensitive device information
-   Scenarios:
    -   Data storage
    -   Data sharing |
|Substitutes specified content in ID card numbers randomly|Code table for randomly substituting administrative region IDs|
|Substitutes specified content in military IDs randomly|Code table for randomly substituting type codes|
|Substitutes specified content in passport numbers randomly|Code table for randomly substituting purpose fields|
|Substitutes specified content in Hong Kong and Macao exit-entry permit numbers randomly|Code table for randomly substituting purpose fields|
|Substitutes specified content in bank card numbers randomly|Code table for randomly substituting Bank Identification Numbers \(BINs\)|
|Substitutes specified content in telephone numbers randomly|Code table for randomly substituting administrative region IDs|
|Substitutes specified content in mobile numbers randomly|Code table for randomly substituting mobile network codes|
|Substitutes specified content in unified social credit codes randomly|Code table for randomly substituting registration authority IDs, code table for randomly substituting type codes, and code table for randomly substituting administrative region IDs|
|Substitutes specified content in general tables with mapped values|Mapping table for substituting uppercase letters, mapping table for substituting lowercase letters, mapping table for substituting digits, and mapping table for substituting special characters|
|Substitutes specified content in general tables randomly|Code table for randomly substituting uppercase letters, code table for randomly substituting lowercase letters, code table for randomly substituting digits, and code table for randomly substituting special characters|
|Rounding|Some of the algorithms are reversible. This type of algorithms can be used to analyze and collect statistics on sensitive datasets.

SDDP provides two types of rounding algorithms. One algorithm rounds numbers and dates, and the operation is irreversible. The other algorithm bit-shifts text, and the operation is reversible.

|Rounds down a number to the Nth digit before the decimal point|Value of N|-   Sensitive data: general sensitive information
-   Scenarios:
    -   Data storage
    -   Data usage |
|Rounds dates|Date rounding level|
|Shifts characters|Number of places by which specified bits are moved and shift direction, which can be left or right|
|Encryption|The algorithms are reversible. This type of algorithms can be used to encrypt sensitive fields that need to be retrieved after encryption.

General symmetrical encryption algorithms are supported.

|Data Encryption Standard \(DES\) algorithm|Encryption key|-   Sensitive data:
    -   Sensitive personal information
    -   Sensitive enterprise information
-   Scenario: data storage |
|Triple Data Encryption Standard \(3DES\) algorithm|Encryption key|
|Advanced Encryption Standard \(AES\) algorithm|Encryption key|
|Shuffling|The algorithms are irreversible. This type of algorithms can be used to de-identify structured data fields.

This type of algorithms extracts values of a field in a specified range from the source table and rearranges the values in the column. Alternatively, this type of algorithms randomly selects values from the column within the value range and rearranges the selected values. This way, the values are mixed up and de-identified.

|Randomly shuffles data|Shuffle method: rearrangement or random selection|-   Sensitive data:
    -   Sensitive device information
    -   Sensitive location information
-   Scenario: data storage |

