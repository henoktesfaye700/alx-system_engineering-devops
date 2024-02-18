# 0x19-postmortem

## Issue Summary

### Duration
Start Time: February 15, 2024, 10:00 PM UTC
End Time: February 16, 2024, 1:00 AM UTC
### Impact
The outage affected our main web application, rendering it inaccessible for approximately 3 hours. Users were unable to log in, access their accounts, or perform any actions within the platform. Approximately 75% of our users were affected by this outage.
### Root Cause
The root cause of the outage was identified as a misconfiguration in the load balancer settings, leading to an imbalance in traffic distribution to backend servers.
### Timeline
10:15 PM UTC: Issue detected through monitoring alerts indicating a spike in server errors.
10:20 PM UTC: The engineering team was notified of the issue.
10:30 PM UTC: Initial investigation focused on backend server health and database performance.
10:45 PM UTC: Assumption made that database overload might be causing the issue.
11:00 PM UTC: Database team engaged to investigate further.
11:30 PM UTC: Database team confirms no issues with database performance.
11:45 PM UTC: Reevaluation of load balancer configuration initiated.
12:15 AM UTC: Load balancer misconfiguration identified as the probable root cause.
12:30 AM UTC: The incident escalated to the infrastructure team for immediate resolution.
1:00 AM UTC: Issue resolved, services restored.
### Root Cause and Resolution
The outage stemmed from a misconfiguration in the load balancer settings, causing an uneven distribution of traffic to backend servers. Consequently, some servers were overwhelmed while others remained underutilized, leading to service degradation. To address this issue, the load balancer configuration was promptly corrected to evenly distribute traffic among backend servers. Additionally, monitoring alerts were updated to promptly flag similar misconfigurations in the future.
### Corrective and Preventative Measures
### Improvements
* Implement regular load balancer configuration audits to catch any misconfigurations early.
* Enhance monitoring alerts to include specific checks for load balancer health and configuration.
* Conduct thorough post-incident reviews to identify any additional areas of improvement in our infrastructure.
### Tasks to Address the Issue
* Conduct a comprehensive review of load balancer configurations across all services.
* Implement automated configuration checks to prevent similar misconfigurations.
* Schedule regular training sessions for the engineering team on load balancer best practices and troubleshooting techniques.
By addressing these corrective measures and implementing preventative actions, we aim to minimize the risk of similar outages in the future and ensure a more robust and resilient infrastructure for our users.
