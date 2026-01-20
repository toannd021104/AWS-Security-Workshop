---
title : "Detective - Overview"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.4.1 </b> "
---

#### Detective - Overview

Amazon Detective helps you analyze, investigate, and quickly identify the root cause of potential security issues or suspicious activity. It automatically collects log data from AWS resources and applies machine learning, statistical analysis, and graph theory to build a connected data set that supports faster and more efficient security investigations.

Amazon Detective streamlines the investigation process and enables security teams to work more effectively. Prebuilt data aggregations, summaries, and contextual insights help you quickly assess the scope and nature of potential security issues. Amazon Detective retains up to one year of aggregated data and presents it through visualizations that show changes in activity type and volume over a selected time range, while linking those changes to security findings. There are no upfront costs, and you pay only for the events analyzed, with no additional software deployment or log configuration required.

Amazon Detective extracts time-based events such as login attempts, API calls, and network traffic from AWS CloudTrail, Amazon Virtual Private Cloud (Amazon VPC) Flow Logs, Amazon GuardDuty findings, AWS Security Hub findings, and Amazon Elastic Kubernetes Service (Amazon EKS) audit logs. Using this data, Detective builds a behavior graph that leverages machine learning to provide a unified, interactive view of resource behavior and interactions over time. By exploring the behavior graph, you can analyze security events such as failed login attempts, suspicious API calls, or related finding groups to support root cause investigation of AWS security findings.

Threat actors often perform a sequence of actions when attempting to compromise an AWS environment, which can generate multiple security findings across different resources. Finding groups are collections of related security findings and resources that represent a single potential security incident and should be investigated together. Finding groups help reduce triage time by allowing you to investigate related findings as a whole rather than individually. You can begin investigations using finding groups to gain a more complete understanding of an incident. Interactive visualizations are also available, allowing you to explore specific findings and insights, including generative AI summaries that describe the sequence of events in natural language.
