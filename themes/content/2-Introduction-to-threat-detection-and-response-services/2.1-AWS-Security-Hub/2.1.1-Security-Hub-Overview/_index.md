---
title: "Security Hub - Overview"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

#### Security Standards

1. Open the [AWS Security Hub Summary page](https://console.aws.amazon.com/securityhub/home?#/summary).

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s1.png)  
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s1b.png)  
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s1c.png)

2. From the **Summary** page, review the security standards currently enabled in your account.  
   For each standard, Security Hub displays the number of controls that have **passed** or **failed**.  
   The compliance percentage represents the ratio of controls in a _Passed_ state compared to all evaluated controls (_Passed_ + _Failed_).

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s2.png)

3. From the left navigation pane, select **Security standards**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s3.png)

4. The security standards shown here were automatically enabled using AWS CloudFormation when the workshop environment was provisioned.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s4.png)

5. To explore a standard in detail, select **View results** for **NIST Special Publication 800-53 Revision 5**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s5.png)

#### Controls

6. At the top of the page, use the status filters to display controls that are **Passed**, **Failed**, **Disabled**, and so on.  
   You can also locate a specific control using the search bar labeled _Filter all enabled controls_.  
   Enter the filter **ID = EC2.13**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s6.png)

7. Select the control titled **Security groups should not allow ingress from 0.0.0.0/0 to port 22**.  
   This view lists all resources evaluated against this control along with their current compliance status.  
   Observe that some resources are marked **FAILED**, while others are marked **PASSED**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s7.png)

8. Each AWS Security Hub control includes remediation guidance.  
   At the top of the page, select the **Remediation instructions** link to open detailed remediation steps in a new browser tab.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s8.png)

#### Investigating a misconfigured resource

9. Return to the selected control.  
   For one of the resources with a **FAILED** status, open the **Config rule** link under the **Investigate** column.  
   This provides direct access to AWS Config for further analysis.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s9.png)

10. Select **Configuration timeline**.  
    This opens AWS Config and displays a timeline of configuration changes for the selected security group.  
    Review the timestamped events to identify when the resource became non-compliant.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s10.png)

11. Expand one of the listed **CloudTrail events**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s11.png)

12. Select **CloudTrail** under _View event_.  
    This opens the corresponding CloudTrail record, which logs account activity across your AWS environment and supports auditing, analysis, and remediation workflows.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s12.png)

#### Consolidated controls

13. Return to Security Hub and open **General settings** from the navigation pane.  
    https://console.aws.amazon.com/securityhub/home?#/settings/general

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s13.png)

14. At the top of the page, confirm that both **Auto-enable new controls in enabled standards** and **Consolidated control findings** are enabled.

15. From the navigation pane, select **Controls**.  
    This view presents a consolidated list of all controls across enabled standards.  
    Consolidation simplifies analysis by showing each control only once, even if it appears in multiple standards, reducing duplicate findings and improving clarity.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s15.png)

#### Insights

16. From the left navigation pane, select **Insights**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s16.png)

17. In the search bar, enter **severity**, then select the insight **24. Severity by counts of findings**.

![VPC](/images/2/2.1-AWS-Security-Hub/s17.png)

18. Security Hub provides several predefined (managed) insights that cannot be modified or deleted.  
    **24. Severity by counts of findings** is one such managed insight.  
    Review the distribution of findings by severity, and select a **Severity label** (for example, _Critical_) to examine the associated findings in detail.

![VPC](/images/2/2.1-AWS-Security-Hub/s18.png)
