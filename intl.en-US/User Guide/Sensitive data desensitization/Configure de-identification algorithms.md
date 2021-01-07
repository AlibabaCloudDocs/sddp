# Configure de-identification algorithms

This topic shows you how to configure de-identification algorithms and provides related examples.

Sensitive Data Discovery and Protection \(SDDP\) supports hashing, redaction, substitution, rounding, encryption, data decryption, and shuffling. For more information, see [Supported data de-identification algorithms](/intl.en-US/FAQ/Supported data de-identification algorithms.md).

## Procedure

1.  Log on to the [SDDP console](https://yundun.console.aliyun.com/?p=sddp#/overview).

2.  In the left-side navigation pane, choose **Data desensitization** \> **Desensitization algorithm**.

3.  Click the tab for the de-identification algorithm that you want to use for static de-identification.

4.  Configure the de-identification algorithm.

    You can configure each de-identification algorithm in the following way:

    -   **Hashing**: Set a salt value for each encryption algorithm.

        **Note:**

        In cryptography, you can insert a specific string to a fixed position in a password so that the hash value of the new password is different from that of the original password. This process is called **salting**. A salt value is the specific string that you insert.

        ![Hashing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63400.png)

    -   **Masking**: Set parameters for the redaction algorithm.

        ![Redaction](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63403.png)

    -   **Replacement**: Set parameters for the substitution algorithm.

        ![Substitution](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63404.png)

    -   **Transformation**: Set parameters for the rounding algorithm.

        ![Rounding](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63409.png)

    -   **Encryption**: Set a key for each encryption algorithm.

        ![Encryption](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63412.png)

    -   **Data decryption**: Set a key for each decryption algorithm.

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p133031.png)

    -   **Shuffling**: Select a shuffling method.

        ![Shuffling](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63413.png)

        **Note:** You do not need to test the shuffling method. Click **Submit** directly after you select a shuffling method.

5.  Click **Test** for a parameter.

    In the Desensitization Algorithm Test panel, check whether the specific parameter for the de-identification algorithm works.

    ![Desensitization Algorithm Test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1844298951/p63402.png)

    After the test is completed, close the Desensitization Algorithm Test panel.

6.  Click **Submit** for the parameter that you have tested.


After you configure the de-identification algorithm, go to the Static Desensitization page to create a de-identification task with the de-identification algorithm or modify the de-identification algorithm of an existing de-identification task. For more information, see [Perform static de-identification](/intl.en-US/User Guide/Sensitive data desensitization/Perform static de-identification.md).

