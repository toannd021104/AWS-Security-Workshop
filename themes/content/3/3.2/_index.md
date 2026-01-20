---
title: "Aggregating findings from multiple AWS accounts"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

When you use Security Hub together with AWS Organizations, you can automatically enable Security Hub across all accounts in your organization, including any new accounts that are added later. This expands the coverage of Security Hub checks and findings, providing a more complete and accurate view of your overall security posture. By using the Security Hub delegated administrator feature in combination with central configuration, you can achieve a centralized security view across AWS services and partner services, spanning multiple accounts and regions.

**Note to readers**: Although this workshop states that multi-account aggregation cannot be demonstrated at this time, the **Automated Security Response on AWS** section includes an architecture diagram showing CloudFormation stacks deployed across multiple AWS accounts.
