---
title: "Inspector  - Findings"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.3.3 </b> "
---

#### Filter findings

1. Navigate to **Findings: All Findings** (https://us-east-1.console.aws.amazon.com/inspector/v2/home?region=us-east-1#/findings/all ).

2. Select the input field at the top of the page labeled **Filter criteria** with the placeholder text “Add filter”. Finding filters allow you to display only findings that match specific criteria, while excluding all others from the view. Take a moment to review the available filtering options.

3. You can apply filters on each tab to narrow the scope to specific types of findings. Try filtering by a resource tag. Click **Add filter**, then select **Resource tag**. Note that filters are case sensitive. Enter **"Environment"** as the Key and **"Development"** as the **Value**, then click **Apply**. This will display findings associated with resources that have the specified tag.

![VPC](/images/2/2.3/2.3.3/s3.png)

4. Remove the filter you just applied by selecting **Clear filters**.

<!--

5. Add a new filter. Click the field, **Add filter**. Select **Resource tag**. Keep in mind, filters are case sensitive. Input "**Name**" for Key. Input "**EC2InstanceDev3**" for **Value**. This will display only findings for EC2 instance(s) named "EC2InstanceDev3". You can optionally try adding multiple filters at the same time to narrow your search.

6. Now remove that filter(s) you just added by clicking **Clear** filters.

#### Reviewing a network reachability finding for EC2

7. Click the field, **Add filter**. Select **Type** and then select **Network Reachability**. Click **Apply**.

8. Click the title of one of the filtered findings to view the finding report. In the finding report, you can see information such as Severity, Open port range, Account ID, information about the resource, and Open Network Paths.

#### Reviewing a code vulnerability finding for Lambda

9. Remove all the filters by clicking **Clear filters**. Click the field, **Add filter**. Select **Type** and then select **Code Vulnerability**. Click **Apply**.

10. Click the title of finding, **CWE-117,93 - Log injection**, to view the finding report.

11. The finding states "User-provided inputs must be sanitized before they are logged. An attacker can use unsensitized input to break a log's integrity, forge log entries, or bypass log monitors." The details in the report include the information about the resource and suggested remediation. Read the suggested remediation. As a challenge, come back later if you have time and try to remediate the issue WITHOUT deleting the function.

12. Close out of the finding and remove all the filters by clicking **Clear filters** again. -->
