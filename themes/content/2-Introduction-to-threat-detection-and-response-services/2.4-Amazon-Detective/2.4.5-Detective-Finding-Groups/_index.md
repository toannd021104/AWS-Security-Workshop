---
title : "Detective - Finding Groups"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.4.5 </b> "
---
Amazon Detective finding groups allow you to examine multiple activities in the context of a potential security event. Finding groups help you analyze the root cause of high-severity GuardDuty findings by bringing together related security signals. When a threat actor attempts to compromise an AWS environment, they typically perform a sequence of actions that generate multiple security findings and unusual behaviors. These actions are often distributed across different points in time and across multiple entities. Investigating findings in isolation can lead to misinterpretation of their importance and make it more difficult to identify the root cause. Amazon Detective addresses this challenge by using graph analysis techniques to infer relationships between findings and entities and grouping them together. Finding groups are recommended as the starting point for investigating related entities and findings.

Detective analyzes finding data and groups findings that are likely related based on shared resources. For example, findings associated with actions performed by the same IAM role session or originating from the same IP address are often part of the same underlying activity. Reviewing findings and evidence as a group provides additional context, even when some associations identified by Detective may not be directly related.

In addition to findings, each finding group includes the entities involved in those findings. These entities can include AWS resources as well as external entities such as IP addresses or user agents.

When an initial GuardDuty finding occurs that is related to another finding, Amazon Detective creates a finding group containing all related findings and associated entities within 48 hours.
