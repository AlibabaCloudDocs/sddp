---
keyword: [SDDP, sensitive data de-identification, de-identification template]
---

# Manage de-identification templates

Sensitive Data Discovery and Protection \(SDDP\) allows you to create de-identification templates to manage de-identification algorithms. You can create a de-identification template and add de-identification algorithms that are frequently used in the same scenario to the template. This avoids repeated configuration of de-identification algorithms and improves the efficiency in sensitive data processing. This topic describes how to manage de-identification templates.

## Create a de-identification template

You can create an unlimited number of de-identification templates.

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Desensitization** \> **Desensitization Template**.

3.  On the Desensitization Template page, click **New Template**.

4.  In the New Template pane, set the parameters as required. The following table describes the parameters for creating a de-identification template.

    ![Create a template](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9744298951/p88406.png)

    |Parameter|Description|
    |---------|-----------|
    |**Template Name**|The name of the de-identification template.|
    |**Template Description**|The description of the de-identification template. You can enter information such as the scenario to which the template is applied.|
    |**Matching Mode**|The mode in which the de-identification template finds its matched sensitive data. Valid values:     -   **Sensitive Type**: If you select this option, you must select the types of sensitive data to be de-identified, such as vehicle identification numbers and unified social credit codes, and the de-identification algorithm for each type of sensitive data.
    -   **Field Name**: If you select this option, you must specify the fields to be de-identified and the de-identification algorithm for each field. |
    |**Rule List**|The rules used to de-identify sensitive data. Select a sensitive data type or enter a field to be de-identified and specify a de-identification algorithm to configure a rule. SDDP supports the following de-identification algorithms.    -   Hashing
    -   Masking
    -   Substitution
    -   Bit shifting
    -   Encryption
    -   Shuffling
    -   Decryption
For more information, see [Supported de-identification algorithms](/intl.en-US/FAQ/Supported de-identification algorithms.md). You can configure multiple rules in a template. To configure more rules, click **Increase Algorithm**. |


## Manage de-identification templates

-   **Edit a de-identification template**

    To edit a de-identification template, find the template on the Desensitization Template page and click **Edit** in the Actions column. In the Edit pane, modify the description or rules of the de-identification template.

    ![Edit a de-identification template](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9744298951/p88415.png)

-   **Delete a de-identification template**

    To delete a de-identification template that is no longer needed, find the template on the Desensitization Template page and click **Delete** in the Actions column.

    **Note:** Deleted de-identification templates cannot be recovered. Exercise caution when you delete templates.


