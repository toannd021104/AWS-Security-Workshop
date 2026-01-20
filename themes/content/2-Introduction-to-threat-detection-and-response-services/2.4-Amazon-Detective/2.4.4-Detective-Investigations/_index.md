---
title : "Detective - Investigations"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4.4 </b> "
---

#### Ientify a resource to investigate

1. Open the **IAM console** and navigate to the **Roles** page.  
https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-1#/roles

2. Search for the role that starts with **"cfn-GuardDutyLabsInfrastructure-GeneralInstanceRole-"**.

3. Select the role name.

![VPC](/images/2/2.4/2.4.4/s3.png)

4. Copy the ARN displayed at the top of the page. You will use this ARN in a later step.

![VPC](/images/2/2.4/2.4.4/s4.png)

#### Running a detective investigation

5. Open the **Investigations** page from the **Detective** console.  
https://us-east-1.console.aws.amazon.com/detective/home?region=us-east-1#investigations

6. On the Investigations page, choose **Run investigation** in the top-right corner.

![VPC](/images/2/2.4/2.4.4/s6.png)

7. In the **Select resource** section, there are three options for starting an investigation. You can run an investigation on a resource recommended by Detective, specify a particular resource, or initiate an investigation from the Detective Search page. Select **Specify an AWS role or user with an ARN**.

8. Under **Select resource type**, choose **AWS role**.

9. In the **Resource ARN** field, paste the ARN of the role identified earlier.

10. Click **Run investigation**.

![VPC](/images/2/2.4/2.4.4/s11.png)

11. Wait for the investigation to complete. The status should change to **Successful** within 2–3 minutes.

![VPC](/images/2/2.4/2.4.4/s12a.png)

12. Select the investigation ID to review the results. Depending on how long the account has been active, you may see a message indicating that no uncommon behavior was observed. If activity has been detected, the report will include an **Indicators of Compromise** section with details about one or more indicators. The investigation summary highlights anomalous indicators that require attention for the selected scope time. This summary helps you more quickly identify potential root causes, recognize patterns, and understand which resources were affected by security events.

![VPC](/images/2/2.4/2.4.4/s12b.png)
![VPC](/images/2/2.4/2.4.4/s12c.png)

If you want additional details about the **IP address** indicator type, you can view the associated TTPs.

![VPC](/images/2/2.4/2.4.4/s12d.png)

Indicators type TTP:

![VPC](/images/2/2.4/2.4.4/s12e.png)
