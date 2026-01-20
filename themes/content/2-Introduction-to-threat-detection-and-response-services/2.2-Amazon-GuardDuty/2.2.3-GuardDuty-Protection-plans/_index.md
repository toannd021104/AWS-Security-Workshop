---
title: "GuardDuty - Protection plans"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.2.3 </b> "
---

#### Prerequisite

Ensure that the EC2 instance is associated with an **SSM Management Role (instance profile)**.  
This role is required for GuardDuty Runtime Monitoring agents to be installed and managed automatically.

For instructions on attaching an instance profile to an EC2 instance, refer to:  
https://docs.aws.amazon.com/systems-manager/latest/userguide/setup-instance-permissions.html#attach-instance-profile

---

#### Amazon S3 protection in Amazon GuardDuty

1. In the GuardDuty console, navigate to **Protection plans** and open the **S3 Protection** page.

2. Verify that **S3 Protection** is enabled.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s2.png)

---

#### EKS Protection in Amazon GuardDuty

3. Under **Protection plans**, open the **EKS Protection** page in the GuardDuty console.

4. Confirm that **EKS Audit Log Monitoring** is enabled.  
    _Note_: The console experience for GuardDuty EKS Runtime Monitoring is now managed as part of the **Runtime Monitoring** feature.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s4.png)

---

#### Runtime Monitoring in Amazon GuardDuty

5. Navigate to the **Runtime Monitoring** page under **Protection plans**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s5.png)

6. Ensure that **Runtime Monitoring** is enabled, along with **Automated agent configuration** for the following compute types:
   - Amazon EKS
   - AWS Fargate (ECS only)
   - Amazon EC2
     ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s6.png)

7. On the Runtime Monitoring page, switch to the **Runtime coverage** tab and review the **Coverage statistics**.  
    While this is outside the scope of this workshop, you can learn more about Runtime Monitoring configuration at:  
    https://docs.aws.amazon.com/guardduty/latest/ug/runtime-monitoring.html
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s7a.png)

_Note_:  
If an EC2 instance shows an **Unhealthy** coverage status with an **Issue** such as **"No Agent Reporting"** or other SSM-related errors,
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/errorSSM.png)
the GuardDuty agent may not have been installed successfully.

You can verify this by checking the log file `/var/log/amzn-guardduty-agent` on the instance (Amazon Linux 2 or Amazon Linux 2023).  
For troubleshooting guidance, see:  
https://docs.aws.amazon.com/guardduty/latest/ug/gdu-assess-coverage-ec2.html#ec2-runtime-monitoring-coverage-issues-troubleshoot

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s7b.png)

---

#### Malware Protection for EC2 in Amazon GuardDuty

8. Open the **Malware Protection** page under **Protection plans** in the GuardDuty console.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s8.png)

9. GuardDuty automatically initiates malware scans when a finding indicates potential malware on an EC2 instance or container workload.  
    Verify that **GuardDuty-initiated malware scan** is enabled.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s9.png)

Below are examples of EC2 malware scan executions:
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s9b.png)

You can also track individual scans using the **Scan ID**:
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s9c.png)

The **EICAR test file** is commonly used to validate malware detection functionality. It is not an actual virus.

10. Scroll down and enable **Retain scanned snapshots when malware is detected**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s10.png)

---

#### RDS Protection in Amazon GuardDuty

11. Navigate to the **RDS Protection** page under **Protection plans**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s11.png)

12. Confirm that **RDS Login Activity Monitoring** is enabled.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s12.png)

---

#### Lambda Protection in Amazon GuardDuty

13. Open the **Lambda Protection** page under **Protection plans**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s13.png)

14. Verify that **Lambda Network Activity Monitoring** is enabled.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s14.png)
