---
title : "Inspector - Suppressing findings"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.3.5 </b> "
---
Use suppression rules to exclude findings that match specific criteria. For example, you can create a rule that suppresses all findings with low vulnerability scores so you can focus on findings that are most critical.

Suppression rules are used only to filter your list of findings and do not affect the generation of findings or prevent Amazon Inspector from creating them.

When Amazon Inspector generates findings that match a suppression rule, those findings are marked as Suppressed. Suppressed findings do not appear in your findings list by default.

Amazon Inspector retains suppressed findings until they are remediated. When a finding is detected as remediated, Amazon Inspector changes its status to Closed and retains it for 7 days.

Suppressed findings are published to AWS Security Hub and Amazon EventBridge as events. You can automatically suppress unwanted findings in Security Hub by updating the finding status through an EventBridge rule.

You cannot create a suppression rule that closes or remediates findings. Suppression rules only control which findings are visible in your list. Suppressed findings can be viewed at any time in the Amazon Inspector console.

Member accounts within an organization cannot create or manage suppression rules.

#### Configure a rule to suppress low vulnerability findings in dev

1. From the Inspector navigation menu on the left, select **Suppression rules**.

2. Click **Create Rule**.

![VPC](/images/2/2.3/2.3.5/s2.png)

3. In the **Name** field, enter **"Low Severity - Dev Environment"**.

4. In the **Description** field, enter **"Suppress all findings with a low severity score for resources tagged with Development"**.

![VPC](/images/2/2.3/2.3.5/s4.png)

5. Under **Suppression rule filters**, select **Severity**, check the **Low** option, and then click **Apply**.

![VPC](/images/2/2.3/2.3.5/s5.png)

6. Add another filter and select **Resource tag** under EC2. Enter **"Environment"** as the key and **"Development"** as the **value**, then click **Apply**.

7. Click **Save**.

Result:

![VPC](/images/2/2.3/2.3.5/s5b.png)

8. You can view suppressed findings on the [**All Findings** page](https://us-east-1.console.aws.amazon.com/inspector/v2/home?region=us-east-1#/findings/all) by changing the dropdown from **Active** to **Suppressed**.
