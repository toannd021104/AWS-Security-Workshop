---
title : "Detective - Summary"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.4.2 </b> "
---
Use the Summary page in Amazon Detective to identify entities that may require investigation based on activity from the previous 24 hours. The Summary page helps highlight entities associated with specific types of unusual behavior and serves as one of several possible starting points for an investigation.

To view the Summary page, select **Summary** from the Detective navigation pane. The Summary page is also displayed by default when you first open the Detective console.

From the Summary page, you can identify entities that meet the following criteria:
- Investigations that indicate potential security events identified by Detective
- Entities involved in activity originating from newly observed geolocations
- Entities that generated the highest number of API calls
- EC2 instances with the highest volume of network traffic
- Container clusters with the largest number of containers

From each panel on the Summary page, you can navigate directly to the profile of a selected entity.

While reviewing the Summary page, you can adjust the **Scope time** to examine activity for any 24-hour period within the previous 365 days. When you update the start date and time, the end date and time are automatically set to 24 hours after the selected start time.

Amazon Detective provides access to up to one year of historical event data. This data is presented through visualizations that illustrate changes in activity type and volume over a selected time range. Detective also correlates these changes with GuardDuty findings.
