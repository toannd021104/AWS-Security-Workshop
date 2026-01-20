---
title: "GuardDuty - Suppressing findings"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.2.5 </b> "
---

#### Configuring a suppression rule for vulnerability assessment tools

1. From the **Amazon GuardDuty** console, navigate to the **Findings** page.

2. Click **Suppress Findings** to begin creating a new suppression rule.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s2.png)

3. The suppression rule will be defined using two filter criteria.  
    For the first criterion, use the **Finding type** attribute with the value **Recon:EC2/Portscan**.  
    In the **Add filter criteria** field, select **Finding Type**, enter **"Recon:EC2/Portscan"**, and click **Apply**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s3.png)

4. After adding the first filter, review the preview section at the bottom of the page.  
   This preview shows which findings would be suppressed by the rule.  
   To avoid unintentionally suppressing important alerts, add a second filter to further restrict the rule.

5. The second filter should identify the instance or instances that run your vulnerability assessment tools.  
    Depending on your environment, this can be based on **Instance image ID** or **Tag value**.  
    Click **Add filter criteria** again, select **Instance Tag Value**, enter **"Scanner"**, and click **Apply**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s5.png)

6. Confirm that the preview now shows only a single finding being suppressed by this rule.

7. In the **Name** field, enter **"VulnerabilityAssessmentTool"**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s7.png)

8. In the **Description** field, enter **"Suppress findings from Vulnerability Assessment Tool."**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s8.png)

9. Click **Save** to create and activate the suppression rule.
