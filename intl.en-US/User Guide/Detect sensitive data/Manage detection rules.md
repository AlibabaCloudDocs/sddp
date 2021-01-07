---
keyword: [Sensitive Data Discovery and Protection, detection rules, sensitive data detection]
---

# Manage detection rules

Sensitive Data Discovery and Protection \(SDDP\) allows you to customize the rules for classifying sensitive data. You can view and configure sensitive data detection rules. This topic shows you how to create and manage custom rules, view built-in rules, and modify a risk level.

## Create a custom rule

SDDP detects sensitive data in objects or tables and generates alerts based on **sensitive data detection rules**. You can create and manage sensitive data detection rules based on your business requirements. To create a custom rule, perform the following steps:

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identification Rules**.

3.  On the Identification Rules page, click **Add rule**.

4.  In the **Add Rule** dialog box, set the rule parameters.

    ![Add Rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5744298951/p66487.png)

    The following table describes the parameters for creating a custom rule.

    |Parameter|Description|
    |---------|-----------|
    |**Rule name**|The name of the custom sensitive data detection rule.|
    |**Rule source**|The default value of this parameter is **Customize**.|
    |**Rule type**|The type of the sensitive data detection rule. Valid values:     -   **Keywords**: The sensitive data detection rule is defined based on the specified keywords.
    -   **Regular expression**: The sensitive data detection rule is defined based on the specified regular expression.
**Note:**

    -   This parameter is set to **Algorithm** for built-in rules. If you have not created custom rules, SDDP detects sensitive data based on the algorithm-based built-in rules.
    -   The built-in rules provided by SDDP apply to mobile numbers and ID card numbers. We recommend that you check the built-in rules provided by SDDP before you create the custom rule. For more information, see [View built-in rules](#section_bm5_yyp_05w). |
    |**Sensitivity level**|The risk level of the sensitive data detection rule. Valid values:     -   **N/A**: unknown risk level
    -   **S1**: low risk level
    -   **S2**: medium risk level
    -   **S3**: high risk level |
    |**Rule classification**|The category to which the sensitive data detection rule belongs. Valid values:     -   Personal and sensitive information
    -   Device sensitive information
    -   Key sensitive information
    -   Sensitive picture information
    -   Sensitive corporate information
    -   Location-sensitive information
    -   Universal sensitive information |
    |**Rules**|Specify the content of the sensitive data detection rule based on the **Rule type** parameter. The content is used to match sensitive fields or text.     -   If the **Rule type** parameter is set to **Keywords**, you must set the **Method** parameter and enter the keyword used to detect sensitive data in the **Keyword/regex match content** field.

Assume that you want to create a custom rule to detect the mobile number 1331234\*\*\*\*. You can set the **Method** parameter to **Contains** and enter 1331234\*\*\*\* in the **Keyword/regex match content** field.

**Note:** The keyword must be a precise value, for example, a specific mobile number, email address, or ID card number.

    -   If the **Rule type** parameter is set to **Regular expression**, you must enter the regular expression in the **Keyword/regex match content** field.

Assume that you want to create a custom rule to detect mobile numbers. You can enter ^\(\(13\[0-9\]\)\|\(14\[5,7\]\)\|\(15\[0-3,5-9\]\)\|\(17\[0,3,5-8\]\)\|\(18\[0-9\]\)\|166\|198\|199\|\(147\)\)\\\\d\{8\}$ in the **Keyword/regex match content** field.

**Note:** After a rule is created, the rule appears in the rule list. However, the rule list does not display the details of the rule. You can click **Details** in the Operation column to view the details of the rule. |

5.  Click **Enable**, **Save**, or **Cancel**.

    -   **Enable**: If you click **Enable**, the rule is created and enabled. SDDP starts to detect sensitive data based on the rule.
    -   **Save**: If you click **Save**, the rule is created but not enabled by default. To enable the rule, you must turn on the switch in the Status column for the rule in the rule list.

        ![Switch](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5744298951/p108007.png)

    -   **Cancel**: If you click Cancel, the rule is not created.
    **Note:**

    -   SDDP detects sensitive data based on all sensitive data detection rules that are enabled.
    -   A rule takes effect after it is created and enabled by default. If you need to temporarily exclude specific data as sensitive data, you can disable the corresponding rule. After you disable the sensitive data detection rule, SDDP no longer classifies the data as sensitive data. We recommend that you enable all sensitive data detection rules.
    -   You can modify and delete custom sensitive data detection rules, but cannot modify or delete the built-in rules.

## View built-in rules

The built-in sensitive data detection rules provided by SDDP apply to common sensitive data, including mobile numbers and ID card numbers. You can view the rule type, name, and risk level of a built-in rule provided by SDDP. You cannot view the rule definition. To view the built-in rules provided by SDDP, perform the following steps:

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identification Rules**.

3.  On the Identification Rules page, set the **Rule source** parameter to **Built-in**.

    ![View built-in rules](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5744298951/p107928.png)

4.  View built-in rules in the list that appears.

    ![List of built-in rules](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5744298951/p107931.png)

    You can view the information about each built-in rule, such as the name, category, source, and type of the rule.

    **Note:** If you have not created custom rules, SDDP detects sensitive data based on the built-in rules. You cannot modify or delete the built-in rules.

5.  To view the details of a built-in rule, find the built-in rule and click **Details** in the Operation column.

    **Note:** You can view the details of a built-in rule but cannot modify or delete the built-in rule.

6.  In the Rule details dialog box, view the details of the built-in rule.

    ![Rule details](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5744298951/p107934.png)

    You can view the name, source, type, risk level, and category of a built-in rule. You cannot view the algorithm or regular expression of a built-in rule. The **Regular Expression** or **Algorithm** field is empty in the Rule Details dialog box.


## Manage custom rules

SDDP allows you to query, view, modify, and delete custom rules. To query, view, modify, or delete custom rules, perform the following steps:

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identification Rules**.

3.  On the Identification Rules page, set the **Rule source** parameter to **Customize**.

4.  On the Identification Rules page, perform the following operations:

    -   **Query sensitive data detection rules**

        Use the filters above the rule list to query rules. To query sensitive data detection rules, set the rule name, classification, source, type, risk level, and status filters, and click **Search**.

        ![Query sensitive data detection rules](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5744298951/p107984.png)

    -   **View the details of a rule**

        Find the rule that you want to view and click **Details** in the Operation column. In the Rule details dialog box, view the details of the rule.

    -   **Modify a custom rule**

        Find the rule that you want to modify and click **Edit** in the Operation column. In the Rule Editing dialog box, modify the parameters of the rule. For more information about parameters, see [Description of parameters for creating a custom rule](#table_3al_u0l_7mq).

    -   **Delete a custom rule**

        Find the rule that you want to delete and click **Delete** in the Operation column. In the Rule delete message, click **OK**.

        **Note:** After you delete a custom rule, SDDP no longer detects sensitive data based on the rule. Exercise caution when you delete a custom rule.


## Modify a risk level

SDDP allows you to modify the name and description of a risk level. To modify a risk level, perform the following steps:

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive data discovery** \> **Identification Rules**.

3.  On the Identification Rules page, click the **Level settings** tab.

4.  Find the risk level that you want to modify and click **Edit** in the Actions column.

5.  In the Sensitivity level dialog box, modify the information in the Sensitivity level and Description fields.

    By default, SDDP marks sensitive data with the following risk levels: **N/A**, **S1**, **S2**, and **S3**. **N/A** indicates an unknown risk level. The severity of S1, S2, and S3 increases in sequence. You can customize the names and descriptions of the four risk levels to classify the sensitive data detected in your data assets based on your business requirements. SDDP provides the following default descriptions for risk levels:

    -   **S1**: low.
    -   **S2**: medium.
    -   **S3**: high.
6.  Click **OK**.

    The modification takes effect immediately after you submit it. To view the modified level names on the **Rule settings** tab, refresh the **Identification Rules** page.


