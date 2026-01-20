---
title: "GuardDuty - Building your own threat list"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.2.4 </b> "
---

#### Implementing a custom threat list using a fictitious IP address

1. Open **Amazon S3** from the AWS Management Console.

2. Locate the S3 bucket whose name contains the string **"-threatlistbucket-"**, then select the bucket.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s2.png)

The following image shows the threat list bucket that was pre-created for the AWS Workshop account.
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s2b.png)

3. Upload the threat list file that you prepared earlier to this S3 bucket.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s3.png)

4. Record the **S3 URI** of the uploaded file.  
    To obtain the URI, open the bucket, select the file, and copy the S3 URI value.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s4.png)

5. Next, register the uploaded file as a threat list in GuardDuty.  
   Return to the **Amazon GuardDuty** console.

6. From the left navigation pane in GuardDuty, select **Lists**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s6.png)

7. Click **Add a threat IP list**.
   ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s7.png)

8. In the **List name** field, provide a descriptive name for the list, such as **"Test Threat List"**.

9. In the **Location** field, paste the S3 URI of the file you uploaded earlier.

10. Select **Plaintext** as the list **Format**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s10.png)

11. Review the acknowledgement, select **I Agree**, and then click **Add list**.

12. After the list is added, it must be activated before it can be used by GuardDuty.  
     Select the newly created list, choose **Actions**, and then click **Activate**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s12.png)

13. A green confirmation banner will appear indicating **"Successfully updated the list..."**, confirming that the threat list is active.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s13.png)
