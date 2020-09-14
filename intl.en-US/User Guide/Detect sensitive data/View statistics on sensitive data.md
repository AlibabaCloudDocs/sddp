# View statistics on sensitive data

Sensitive Data Discovery and Protection \(SDDP\) can detect sensitive data in MaxCompute, Relational Database Service \(RDS\), Object Storage Service \(OSS\), Tablestore, user-created databases hosted on Elastic Compute Service \(ECS\) instances, PolarDB-X, and PolarDB. This topic describes how to view statistics on sensitive data detected by SDDP in the preceding services.

## View statistics on sensitive data detected in OSS

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the OSS tab, find the target OSS bucket and click **File Details** in the Actions column.

4.  In the right-side pane that appears, you can view the proportion of sensitive objects at each risk level, top five rules that are hit, and the list of objects with sensitive data detected.

    ![Statistics on sensitive data detected in OSS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1744298951/p109786.png)

    -   **Proportion of sensitive objects at each risk level**

        In the **Proportion of Sensitive Files** section, you can view a pie chart that displays the proportions of sensitive objects at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of objects with sensitive data detected**

        In the object list, you can view the information about the objects with sensitive data detected, including the object name, size, type, and number of sensitive fields detected in the object. You can also click **Hit Details** in the Actions column for an object to view the details of the rules that the object hits.


## View statistics on sensitive data detected in RDS

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the Sensitive Data Assets page, click the **RDS** tab.

4.  On the RDS tab, find the target RDS database and click **Table Details** in the Actions column.

5.  In the right-side pane that appears, you can view the proportion of sensitive tables at each risk level, top five rules that are hit, and the list of tables with sensitive data detected.

    ![Statistics on sensitive data detected in RDS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2744298951/p109789.png)

    -   **Proportion of sensitive tables at each risk level**

        In the **Proportion of Sensitive Tables** section, you can view a pie chart that displays the number and proportion of sensitive tables at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of tables with sensitive data detected**

        In the table list, you can view the information about the tables with sensitive data detected, including the table name, total number of rows, total number of fields, number of sensitive fields, and specific sensitive data. You can also click **Column Details** in the Actions column for a table to view field details, including the fields that hit sensitive data detection rules and the risk levels of the sensitive fields.


## View statistics on sensitive data detected in MaxCompute

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the Sensitive Data Assets page, click the **MaxCompute** tab.

4.  On the MaxCompute tab, find the target MaxCompute project and click **Table Details** in the Actions column.

5.  In the right-side pane that appears, you can view the proportion of sensitive tables at each risk level, top five rules that are hit, and the list of tables with sensitive data detected.

    ![Statistics on sensitive data detected in RDS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2744298951/p109789.png)

    -   **Proportion of sensitive tables at each risk level**

        In the **Proportion of Sensitive Tables** section, you can view a pie chart that displays the number and proportion of sensitive tables at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of tables with sensitive data detected**

        In the table list, you can view the information about the tables with sensitive data detected, including the table name, total number of rows, total number of fields, number of sensitive fields, and specific sensitive data. You can also click **Column Details** in the Actions column for a table to view field details, including the fields that hit sensitive data detection rules and the risk levels of the sensitive fields.


## View statistics on sensitive data detected in user-created databases hosted on ECS instances

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the Sensitive Data Assets page, click the **ECS Self-built Database** tab.

4.  On the ECS Self-built Database tab, find the target database and click **Table Details** in the Actions column.

5.  In the right-side pane that appears, you can view the proportion of sensitive tables at each risk level, top five rules that are hit, and the list of tables with sensitive data detected.

    ![Statistics on sensitive data detected in RDS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2744298951/p109789.png)

    -   **Proportion of sensitive tables at each risk level**

        In the **Proportion of Sensitive Tables** section, you can view a pie chart that displays the number and proportion of sensitive tables at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of tables with sensitive data detected**

        In the table list, you can view the information about the tables with sensitive data detected, including the table name, total number of rows, total number of fields, number of sensitive fields, and specific sensitive data. You can also click **Column Details** in the Actions column for a table to view field details, including the fields that hit sensitive data detection rules and the risk levels of the sensitive fields.


## View statistics on sensitive data detected in PolarDB-X

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the Sensitive Data Assets page, click the **DRDS** tab.

4.  On the DRDS tab, find the target database and click **Table Details** in the Actions column.

5.  In the right-side pane that appears, you can view the proportion of sensitive tables at each risk level, top five rules that are hit, and the list of tables with sensitive data detected.

    ![Statistics on sensitive data detected in RDS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2744298951/p109789.png)

    -   **Proportion of sensitive tables at each risk level**

        In the **Proportion of Sensitive Tables** section, you can view a pie chart that displays the number and proportion of sensitive tables at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of tables with sensitive data detected**

        In the table list, you can view the information about the tables with sensitive data detected, including the table name, total number of rows, total number of fields, number of sensitive fields, and specific sensitive data. You can also click **Column Details** in the Actions column for a table to view field details, including the fields that hit sensitive data detection rules and the risk levels of the sensitive fields.


## View statistics on sensitive data detected in PolarDB

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the Sensitive Data Assets page, click the **PolarDB** tab.

4.  On the PolarDB tab, find the target database and click **Table Details** in the Actions column.

5.  In the right-side pane that appears, you can view the proportion of sensitive tables at each risk level, top five rules that are hit, and the list of tables with sensitive data detected.

    ![Statistics on sensitive data detected in RDS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2744298951/p109789.png)

    -   **Proportion of sensitive tables at each risk level**

        In the **Proportion of Sensitive Tables** section, you can view a pie chart that displays the number and proportion of sensitive tables at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of tables with sensitive data detected**

        In the table list, you can view the information about the tables with sensitive data detected, including the table name, total number of rows, total number of fields, number of sensitive fields, and specific sensitive data. You can also click **Column Details** in the Actions column for a table to view field details, including the fields that hit sensitive data detection rules and the risk levels of the sensitive fields.


## View statistics on sensitive data detected in Tablestore

You can view statistics on sensitive data detected in Tablestore.

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Sensitive Data Identification** \> **Sensitive Data Assets**.

3.  On the Sensitive Data Assets page, click the **OTS** tab.

4.  On the OTS tab, find the target Tablestore instance and click **Table Details** in the Actions column.

5.  In the right-side pane that appears, you can view the proportion of sensitive tables at each risk level, top five rules that are hit, and the list of tables with sensitive data detected.

    ![Statistics on sensitive data detected in RDS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2744298951/p109789.png)

    -   **Proportion of sensitive tables at each risk level**

        In the **Proportion of Sensitive Tables** section, you can view a pie chart that displays the number and proportion of sensitive tables at the low, medium, high, and unknown risk levels, respectively.

    -   **Top five rules that are hit**

        In the **Hit Rule Top 5** section, you can view the top five rules that are hit and the number of times that each rule is hit.

    -   **List of tables with sensitive data detected**

        In the table list, you can view the information about the tables with sensitive data detected, including the table name, total number of rows, total number of fields, number of sensitive fields, and specific sensitive data. You can also click **Column Details** in the Actions column for a table to view field details, including the fields that hit sensitive data detection rules and the risk levels of the sensitive fields.


## References

-   [FAQ about sensitive data scan and detection](/intl.en-US/FAQ/FAQ about sensitive data scan and detection.md)
-   [Supported sensitive data](/intl.en-US/FAQ/Supported sensitive data.md)
-   [Supported unstructured files](/intl.en-US/FAQ/Supported unstructured files.md)

