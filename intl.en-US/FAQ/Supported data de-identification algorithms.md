# Supported data de-identification algorithms

This topic describes the data de-identification algorithms that are supported by Data Security Center \(DSC\).

|Category|Description|Algorithm|Input|Applicable sensitive data and scenario|
|--------|-----------|---------|-----|--------------------------------------|
|Hashing|The algorithms are irreversible. This type of algorithms is applicable to password protection or the scenario in which you must check whether data is sensitive by comparison.

You can use common hash algorithms and set the salt value.

|MD5|Salt value|-   Sensitive data: key information
-   Scenario: data storage |
|Secure Hash Algorithm 1 \(SHA-1\)|Salt value|
|SHA-256|Salt value|
|Hash-based Message Authentication Code \(HMAC\)|Salt value|
|Redaction by using asterisks \(\*\) or number signs \(\#\)|The algorithms are irreversible. This type of algorithms is applicable to the scenario in which sensitive data is to be shown on the user interface or is to be shared with others.

This type of algorithms redacts specified text in sensitive data with asterisks \(\*\) or number signs \(\#\).

|Keeps the first N characters and the last M characters|Values of N and M|-   Sensitive data: sensitive personal information
-   Scenarios:
    -   Data usage
    -   Data sharing |
|Keeps characters from the Xth position to the Yth position|Values of X and Y|
|Redacts the first N characters and the last M characters|Values of N and M|
|Redacts characters from the Xth position to the Yth position|Values of X and Y|
|Redacts characters before a special character when the special character appears for the first time|At sign \(@\), ampersand \(&\), or period \(.\)|
|Redacts characters after a special character when the special character appears for the first time|At sign \(@\), ampersand \(&\), or period \(.\)|
|Substitution, which supports customization|Some of the algorithms are reversible. This type of algorithms can be used to de-identify fields in fixed formats, such as ID card numbers.

This type of algorithms substitutes the entire value or a part of the value of a field with the mapped value by using a mapping table or randomly based on a random interval. The substitution based on a mapping table is reversible, whereas the substitution based on a random interval is irreversible. DSC provides multiple built-in mapping tables and allows you to customize substitution algorithms.

|Substitutes specified content in ID card numbers with mapped values|Mapping table for substituting administrative region IDs|-   Sensitive data:
    -   Sensitive personal information
    -   Sensitive enterprise information
    -   Sensitive device information
-   Scenarios:
    -   Data storage
    -   Data sharing |
|Randomly substitutes specified content in ID card numbers|Code table for randomly substituting administrative region IDs|
|Randomly substitutes specified content in military IDs|Code table for randomly substituting type codes|
|Randomly substitutes specified content in passport numbers|Code table for randomly substituting purpose fields|
|Randomly substitutes specified content in permit numbers of Exit/Entry Permits for Travelling to and from Hong Kong and Macau|Code table for randomly substituting purpose fields|
|Randomly substitutes specified content in bank card numbers|Code table for randomly substituting Bank Identification Numbers \(BINs\)|
|Randomly substitutes specified content in telephone numbers|Code table for randomly substituting administrative region IDs|
|Randomly substitutes specified content in mobile numbers|Code table for randomly substituting mobile network codes|
|Randomly substitutes specified content in unified social credit codes|Code table for randomly substituting registration authority IDs, code table for randomly substituting type codes, and code table for randomly substituting administrative region IDs|
|Substitutes specified content in general tables with mapped values|Mapping table for substituting uppercase letters, mapping table for substituting lowercase letters, mapping table for substituting digits, and mapping table for substituting special characters|
|Randomly substitutes specified content in general tables|Code table for randomly substituting uppercase letters, code table for randomly substituting lowercase letters, code table for randomly substituting digits, and code table for randomly substituting special characters|
|Rounding|Some of the algorithms are reversible. This type of algorithms can be used to analyze and collect statistics on sensitive datasets.

DSC provides two types of rounding algorithms. One algorithm rounds numbers and dates, and the operation is irreversible. The other algorithm bit-shifts text, and the operation is reversible.

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

