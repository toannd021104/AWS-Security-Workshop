---
title: "Inspector - Overview"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.3.1 </b> "
---

#### Inspector

Amazon Inspector is a continuous vulnerability management service designed to scan AWS workloads for software vulnerabilities and unintended network exposure. With minimal setup through the AWS Management Console, the service can be enabled across all accounts within an AWS Organization. Once activated, Inspector automatically discovers supported resources at scale, including Amazon EC2 instances, container images stored in Amazon ECR and used within CI/CD pipelines, as well as AWS Lambda functions, and immediately begins assessing them against known vulnerability databases.

For each identified issue, Amazon Inspector calculates a contextual risk score by correlating Common Vulnerabilities and Exposures (CVE) information with environmental factors such as network accessibility and exploitability. These scores help security teams prioritize remediation by focusing first on the vulnerabilities that pose the highest risk. All findings are aggregated and presented in the Amazon Inspector console and are automatically forwarded to AWS Security Hub and Amazon EventBridge to support centralized visibility and workflow automation. In addition, vulnerabilities detected in container images are reported directly to Amazon ECR, enabling resource owners to review and remediate issues within their existing operational workflows. Through this approach, Amazon Inspector enables organizations of all sizes to maintain consistent workload security and compliance across their AWS environments.

![VPC](/images/2/2.3/2.3.1/s1.png)
