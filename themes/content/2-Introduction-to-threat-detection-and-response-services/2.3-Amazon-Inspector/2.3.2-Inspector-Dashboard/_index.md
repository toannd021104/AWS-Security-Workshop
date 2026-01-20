---
title: "Inspector - Dashboard"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.3.2 </b> "
---

#### Check out the Inspector dashboard

1. Open the Inspector **Dashboard** at: https://us-east-1.console.aws.amazon.com/inspector/v2/home?region=us-east-1#/dashboard

2. At the top of the page, review the **Environment coverage** section. Observe that only a percentage of instances are currently covered. You can optionally select the percentage value to view details about which instances are being scanned.

![VPC](/images/2/2.3/2.3.2/s2.png)

3. On the dashboard, locate **Risk Based Remediations** near the top of the page. This section highlights the top five software packages with critical vulnerabilities that affect the largest number of resources in your environment. Addressing these packages can significantly reduce overall critical risk. Select a software package name to view related vulnerability details and impacted resources.

![VPC](/images/2/2.3/2.3.2/s3.png)

4. On the dashboard, you can also review the following:

- Amazon ECR repositories with most critical findings
- Amazon ECR container images with most critical findings
- Amazon EC2 Instances with most critical findings
- Amazon Machine Images (AMI) with most critical findings
- AWS Lambda functions with the most critical findings
- Code detectors for Lambda code scanning

![VPC](/images/2/2.3/2.3.2/s4.png)

Review some of the findings and select one to view additional details.

![VPC](/images/2/2.3/2.3.2/e1.png)

Additional information is displayed for the selected finding.

![VPC](/images/2/2.3/2.3.2/e2.png)

You can select individual techniques to view more detailed information.

![VPC](/images/2/2.3/2.3.2/e3.png)
