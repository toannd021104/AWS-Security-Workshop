---
title : "Cross-region finding aggregation"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

With cross-Region aggregation, you can collect findings, finding updates, insights, control compliance statuses, and security scores from multiple Regions into a single aggregation Region. All aggregated data can then be managed centrally from that aggregation Region.

For example, if you configure US East (N. Virginia) as the aggregation Region and US West (Oregon) and US West (N. California) as linked Regions, the Findings page in US East (N. Virginia) will display findings from all three Regions. Updates to findings are reflected across all Regions. Control enablement must still be managed per Region. If a control is enabled in a linked Region but disabled in the aggregation Region, you can view its compliance status from the aggregation Region, but you cannot enable or disable that control there.

#### Set up cross-region finding aggregation

1. You may have already seen a prompt to **Configure finding aggregation**. You can select any of these prompts to begin the setup. If you did not see the prompt, open the **Regions** page under **Settings** from the navigation menu on the left.

2. Click **Configure finding aggregation**.

![VPC](/images/3/3.4/s2.png)

3. Select **US East (N. Virginia) - us-east-1** as the aggregation Region.

4. Select all available Regions.

6. Click **Save** at the bottom of the page. This enables cross-region aggregation of findings but does not enable Security Hub in the other Regions.

![VPC](/images/3/3.4/s6.png)

**Note to Participants**: When you click **Save** to enable cross-region aggregation, aggregated scores and control data in Security Hub are reset. Findings are not removed and continue to be generated, but scores will not appear (for example, on the Summary page) until new scores are calculated across multiple Regions. You may want to complete the workshop section titled **Security Posture Management** before completing this module.

#### Turn on the AWS security services you use in the linked Region

Although many AWS security services are already enabled in us-east-1 (N. Virginia) and finding aggregation has been configured in Security Hub, this does not automatically enable those services in other Regions. To quickly enable the same AWS security services in us-east-2 (Ohio), use CloudFormation to deploy the required resources in the second Region. Once enabled, findings from those services are automatically aggregated into Security Hub in us-east-1 (N. Virginia) based on the configuration completed earlier.

7. Open the following page in the CloudFormation console:  
https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/?filteringText=cfn&filteringStatus=active&viewNested=false

![VPC](/images/3/3.4/s7.png)

8. Click the stack named **cfn**.

![VPC](/images/3/3.4/s8.png)

9. Open the **Outputs** tab.

![VPC](/images/3/3.4/s9.png)

10. Select **SecurityServicesCloudFormationLink** to launch a preconfigured CloudFormation template in us-east-2 (Ohio). This opens the **Quick create stack** page in us-east-2 (Ohio) with stack details and parameters pre-filled. Confirm that the Region shown in the top-right corner is **Ohio**.

11. Leave the default values for **Stack name**, **MyAssetsBucketName**, and **MyAssetsBucketPrefix**. If these values are not populated, ask your facilitator.

![VPC](/images/3/3.4/s11.png)

12. At the bottom of the page, select the checkboxes acknowledging that AWS CloudFormation may create IAM resources with custom names and may require the capability **CAPABILITY_AUTO_EXPAND**.

13. Click **Create stack**. This enables AWS Config, Security Hub, Inspector, Detective, Macie, and GuardDuty in us-east-2 (Ohio). Because cross-region aggregation is already configured, findings generated in this Region will automatically appear in the aggregation Region. This process may take a few minutes, and you can continue without waiting.

![VPC](/images/3/3.4/s13.png)

14. Return to Security Hub. If you are not already in the original workshop Region, a prompt to **Go to aggregation region** appears. Select it and confirm that you are back in us-east-1 (N. Virginia), indicated by **N. Virginia** in the top-right corner.

15. After returning to Security Hub in the aggregation Region, the Findings page now includes findings from multiple Regions, and the Summary page visualizations reflect cross-region data. These views will be explored further later in the workshop.

(After 5 minute)

![VPC](/images/3/3.4/s15.png)
