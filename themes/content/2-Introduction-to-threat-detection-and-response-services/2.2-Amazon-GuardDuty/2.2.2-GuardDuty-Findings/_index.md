---
title: "GuardDuty - Findings"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2.2 </b> "
---

A GuardDuty finding represents a potential security concern identified within your AWS environment. GuardDuty generates a finding whenever it detects unexpected, suspicious, or potentially malicious activity based on its analysis of account and workload telemetry. Findings can be reviewed and managed through the GuardDuty console, or programmatically by using the GuardDuty CLI or API.

#### Review a GuardDuty finding

1. Open the **Findings** page in Amazon GuardDuty by selecting **Findings** from the navigation panel on the left.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s1.png)

Below is an example of findings in the AWS Workshop account:
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s1b.png)

2. Select a finding from the list by clicking on its row. This opens the finding summary panel on the right side of the page. The information displayed varies depending on the finding type.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s2.png)

Another example finding in the workshop environment:
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s2b.png)

3. Take a moment to review the details of the selected finding, including the description and affected resources.

#### Understanding GuardDuty finding severity

4. Locate the **Severity** value associated with the selected finding. Severity indicates the relative risk level of the detected activity.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s4.png)

5. To view or download the finding in JSON format, select the **Finding ID** link at the top of the finding summary panel.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s5a.png)

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s5b.png)

6. Close the finding summary by clicking the **X** icon in the upper-right corner.

#### Searching and filtering GuardDuty findings

7. Click the search field labeled **Add filter criteria** at the top of the findings list.

8. Enter **Severity** in the search field and select **Severity** from the dropdown. A submenu appears with the available severity levels: Low, Medium, and High.

9. Select **High** and click **Apply**. The findings list updates to display only findings with high severity.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s9a.png)

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s9b.png)

#### Managing GuardDuty findings

10. With a finding selected, open the **Actions** menu in the upper-right corner and choose **Archive** to archive the finding.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s10.png)

11. Archived findings are removed from the list of current findings. To view them, open the **Current** dropdown and select **Archived**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s11a.png)

Result:
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s11b.png)

12. To restore an archived finding, select it from the archived list, open the **Actions** menu again, and choose **Unarchive**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s2.png)
