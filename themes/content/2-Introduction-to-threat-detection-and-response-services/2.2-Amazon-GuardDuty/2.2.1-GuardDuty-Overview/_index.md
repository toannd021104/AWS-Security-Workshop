---
title : "GuardDuty - Overview"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.2.1 </b> "
---

#### GuardDuty - Overview

Amazon GuardDuty is a managed threat detection service that continuously analyzes activity across your AWS environment to identify malicious behavior and unauthorized actions. The service leverages a combination of machine learning (ML), statistical anomaly detection, and threat intelligence from AWS and trusted third-party sources to help protect AWS accounts, workloads, and data.

GuardDuty is designed to operate at scale, analyzing tens of billions of events per day from multiple AWS data sources. These sources include AWS CloudTrail logs, Amazon Virtual Private Cloud (VPC) Flow Logs, and DNS query logs. In addition, GuardDuty extends its monitoring capabilities to Amazon Simple Storage Service (Amazon S3) data events, Amazon Aurora database login activity, and runtime activity from compute and container services such as Amazon Elastic Compute Cloud (EC2), Amazon Elastic Container Service (ECS), AWS Fargate, and Amazon Elastic Kubernetes Service (EKS).

One of the core strengths of GuardDuty is its ability to detect signs of account compromise that are difficult to identify through manual or periodic inspection. Examples include access to AWS resources from unusual geographic locations, activity occurring at atypical times, or anomalous API behavior. For programmatic access, GuardDuty can identify suspicious API calls, such as attempts to disable CloudTrail logging to conceal activity or unauthorized snapshot creation originating from known malicious IP addresses.

GuardDuty continuously evaluates account-level and workload-level events without requiring any additional software installation or infrastructure management. Foundational protections are enabled natively by analyzing existing AWS log sources. When multiple AWS accounts are associated, GuardDuty enables centralized threat detection, allowing findings to be aggregated and reviewed across accounts rather than managed individually.

By removing the need to manually collect, correlate, and analyze large volumes of security telemetry, GuardDuty allows security teams to focus on timely investigation and response, improve overall security posture, and continue scaling their workloads securely on AWS.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.1-GuardDuty-Overview/s1.png)
