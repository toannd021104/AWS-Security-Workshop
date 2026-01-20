---
title: "Centralizing findings from AWS security services"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

Security Hub automatically collects and consolidates findings from AWS security services enabled in your environment, such as intrusion detection findings from Amazon GuardDuty, vulnerability scan results from Amazon Inspector, Amazon Simple Storage Service (Amazon S3) bucket policy findings from Amazon Macie, publicly accessible and cross-account resource findings from IAM Access Analyzer, and resources without WAF coverage identified by AWS Firewall Manager.

This aggregation provides a unified view of security and compliance across your AWS environment. AWS Security Hub brings together security findings from dozens of AWS security services and APN products into a single location and standardized format known as the AWS Security Finding Format (ASFF). Security Hub does not retroactively ingest findings that were generated before it was enabled. All findings are retained in Security Hub for 90 days from their last update.

The Integrations page in the AWS Management Console provides access to all available AWS and third-party product integrations. The AWS Security Hub API also includes operations for managing integrations. For AWS services, integrations are enabled automatically, and you can optionally disable individual integrations if needed.

#### Centralizing findings from AWS security services

1. Navigate to Security Hub and open the Summary page. The [Security Hub Summary page](https://us-east-1.console.aws.amazon.com/securityhub/home?region=us-east-1#/summary) provides an overview of the security and compliance status of your AWS account.

2. Spend a few minutes reviewing the insights displayed on the Summary page. Can you identify the most common threat types detected in your environment? These findings are aggregated into Security Hub from Amazon GuardDuty.

![VPC](/images/3/3.1/s2.png)

3. Open the Integrations page in Security Hub and scroll through the available integrations.

![VPC](/images/3/3.1/s3a.png)
![VPC](/images/3/3.1/s3b.png)

As shown, many integrations, including **Amazon: GuardDuty** and **Amazon: Inspector**, are automatically enabled. However, each service must also be enabled independently to generate findings.

4. Security Hub allows you to enable or disable AWS integrations. Although this is not typically recommended, try disabling the **AWS: Firewall Manager** integration by clicking **Stop accepting findings** in the **AWS: Firewall Manager** integration box.

![VPC](/images/3/3.1/s5a.png?featherlight=false&width=10pc)

5. A confirmation popup appears stating that Security Hub will no longer ingest findings from this integration, even though the product may continue sending them. Click **Cancel** to keep the integration enabled.

![VPC](/images/3/3.1/s5b.png)

6. To view findings from a specific service, locate the **Amazon: GuardDuty** integration and click **See findings**. This opens the Findings page with a filter applied to display only GuardDuty findings. Remain on the Findings page.

7. You can optionally remove or modify filters to adjust the list of displayed findings.

#### Searching and reviewing security findings

8. To view all findings in Security Hub, remove all filters (and **Group By**, if present) by clicking the **X** next to each filter at the top of the page.

9. The findings list may be extensive. Add a filter to narrow the results to high-severity findings from the GuardDuty threat detection service. Click **Add filters** in the search bar.

10. From the dropdown, select **Severity label**, choose **is**, and enter **HIGH**. This field is case sensitive. Click **Apply**.

![VPC](/images/3/3.1/s10a.png)

Result:

![VPC](/images/3/3.1/s10b.png)

Choose one finding to review additional details.

![VPC](/images/3/3.1/s10c.png)

11. Click **Add filters** again. Select **Product name**, choose **is**, and enter **GuardDuty**. Click **Apply**.

12. Select one of the findings and click its title to open the finding details pane. Expand each section and review the available information, including the description, remediation guidance, and resource details.

13. In the finding details pane, click the **Finding ID** link at the top to display the complete JSON representation of the finding. Security Hub uses the AWS Security Finding Format (ASFF) to standardize findings and eliminate the need for manual data conversion. The JSON can be downloaded for further analysis if needed.

![VPC](/images/3/3.1/s13.png)

14. Close the JSON view by clicking the **X** in the top-right corner.

15. At the top of the finding details pane, open the **History** tab to view a chronological record of changes made to the finding. Reviewing the history helps you understand how a finding has evolved over time.

16. Close the finding details pane by clicking the **X** in the top-right corner, but remain on the Findings page.

17. To understand which resources are generating the most findings, remove all filters. Then add a new filter by selecting **Resource type**, choosing **is not**, and entering **AwsAccount**. Click **Apply**.

![VPC](/images/3/3.1/s17a.png)

Result:

![VPC](/images/3/3.1/s17b.png)

18. Add another filter. Select **Record state**, choose **is**, and enter **ACTIVE**. Click **Apply**.

![VPC](/images/3/3.1/s18.png)

19. Click **Add filters** again. This time, select **Group by** and choose **ResourceId**, then click **Apply**. The results now show the number of security findings per resource, which can help you prioritize remediation efforts.

![VPC](/images/3/3.1/s19.png)

Result:

![VPC](/images/3/3.1/s19b.png)

#### Generating insights from aggregated findings

20. If this grouped view is useful, you can save it as a custom Insight for future reference. Click **Create insight** in the top-right corner of the page.

21. Name the insight **"0. Resources by counts of findings"**, then click **Create insight**.

![VPC](/images/3/3.1/s20.png)

22. From the navigation menu on the left, select **Insights**. An Insight in Security Hub is a collection of related findings defined by aggregation logic and optional filters. Insights help highlight security areas that require attention. Security Hub provides several managed insights that cannot be modified or deleted, and also allows you to create custom insights tailored to your environment.

23. The first insight listed is the one you just created. Click **0. Resources by counts of findings** to view the aggregated results along with generated visualizations.

![VPC](/images/3/3.1/s23.png)

24. Return to the Insights page using the navigation menu on the left.

25. Spend a few minutes reviewing the other AWS-provided Insights. Apply filters to view insights by severity.

26. Select **24. Severity by counts of findings**.

27. Choose a **Severity Label** (for example, **Critical**) to view the underlying finding or findings.

![VPC](/images/3/3.1/s26.png)

Result:

![VPC](/images/3/3.1/s26b.png)
