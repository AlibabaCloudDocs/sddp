---
keyword: [sensitive data de-identification, de-identification template]
---

# Manage de-identification templates

Data Security Center \(DSC\) supports custom de-identification templates. You can create a de-identification template and add de-identification algorithms that are frequently used in the same scenario to the template. This avoids repeated configuration of de-identification algorithms and improves the efficiency in sensitive data processing. This topic describes how to create and manage de-identification templates.

## Create a de-identification template

You can create an unlimited number of de-identification templates.

1.  Log on to the [DSC console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Data desensitization** \> **Desensitization Template**.

3.  On the Desensitization Template page, click **New template**.

4.  In the New template panel, set the parameters as required. The following table describes the parameters for creating a de-identification template.

    ![Create a template](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9744298951/p88406.png)

    |Parameter|Description|
    |---------|-----------|
    |**Template name**|The name of the de-identification template.|
    |**Template description**|The description of the de-identification template. You can enter information such as the scenario to which the de-identification template is applied.|
    |**Matching mode**|The mode in which the de-identification template finds its matched sensitive data. Valid values:    -   **Sensitive type**: If you select this option, you must select a sensitive data type that is supported by DSC, such as vehicle identification number and unified social credit code, and a de-identification algorithm for the sensitive data type.
    -   **Field name**: If you select this option, you must specify the field to be de-identified and select a de-identification algorithm for the field. |
    |**Rule list**|Select a sensitive data type or enter a field to be de-identified and specify a de-identification algorithm. DSC supports the following de-identification algorithms:    -   Hashing
    -   Redaction
    -   Substitution
    -   Rounding
    -   Encryption
    -   Shuffling
    -   Data decryption
For more information, see [Supported data de-identification algorithms](/intl.en-US/FAQ/Supported data de-identification algorithms.md). You can configure multiple rules in a template. To configure more rules, click **Increase algorithm**. |


## Manage de-identification templates

-   **Modify a de-identification template**

    To update the description or rules of a de-identification template, find the template on the Desensitization Template page and click **Edit** in the Actions column. In the Edit panel, modify the description or rules of the template.

    ![Modify a de-identification template](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9744298951/p88415.png)

-   **Delete a de-identification template**

    To delete a de-identification template that is no longer applicable to the current business scenario, find the template on the Desensitization Template page and click **Delete** in the Actions column.

    **Note:** Deleted templates cannot be recovered. Exercise caution when you delete templates.


