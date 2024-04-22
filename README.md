## AAD-Logging-Monitoring
![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/ece88708-7422-45d2-b759-aab2dc34c84f)
## Introduction

In the previous project, KAFFCO Estate, a fictional company, implemented an Azure-based honeynet accessible on the Internet to attract hackers. Various log sources were gathered in a Log Analytics workspace, enabling Microsoft Sentinel to generate attack maps, alerts, and incidents. Initial security metrics were assessed over a 24-hour period within this vulnerable setup. Following this, security controls were introduced to bolster the environment, and metrics were reassessed for another 24 hours. Among these logs were Azure Active Directory Logs, which capture the complete sign-in activity history and maintain an audit trail of all activities and changes within Azure AD for a specific tenant. These logs provide comprehensive details on sign-in and audit activities, offering insights into modifications within the Active Directory. To seamlessly transmit these sign-in and audit logs to the Log Analytics workspace, configuring the AAD diagnostic setting accordingly will be necessary.
## Step-By-Step Configuration Of Azure AD Logging
![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/bf3c5b97-dac9-49ed-bbf0-3a3ade2d349d)
1.	From the Azure home page, search for Azure Active Directory in the search bar.
2.	Click to open the Azure Active Directory from the drop-down menu.
![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/9a56ad35-70c4-4a9c-9980-610ff697b20d)
3.	From the Azure Active Directory page
4.	Click Diagnostic setting and then.
5.	Click Add diagnostic setting to configure the Diagnostic setting.
![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/8272dc77-0470-4568-ad4c-82acebe2e8d0)
6.	Give the Diagnostic setting a name by entering a name. In this case, the name is "AAD-Logs”.
7.	Select from the Logs categories which Logs you want to collect i.e.: Audit Logs, Signing logs, Managed Identity Signing Logs, Risky Users, etc...
8.	Select the destination for the selected logs. In this case, they are sent to the Log Analytics workspace.
9.	Select the appropriate Subscription. In this case "KAFFCOEstateProject"
10.	Select the appropriate Logs Analytics workspace. In this case, "Log AnalyticsREP" which resides in the east US 2
11.	Click Save to create the Diagnostic setting for Azure Active Directory Tenant

## Test To Ensure The Logs Have Been Ingested Into The Logs Analytics Workspace

![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/969832d0-9bdb-45e6-8525-8c89c6f3cb2f)

1.	From the Azure home page, search for Log Analytics workspace in the search bar.
2.	Click to open the Log Analytics workspace from the drop-down menu.

![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/5bf6a386-a39b-4375-aca2-98bd0cfc7c2d)

3.	From the Log Analytics workspace page
4.	Click Logs to access the query page.
5.	Type Audit Logs (Audit Logs is one of the Logs categories selected to be sent to the Log Analytics workspace)
6.	Click Run to run the Audit Logs query.
7.	The results of the query are populated in the Log Analytics workspace.
![image](https://github.com/LawsonSecOps/AAD-Logging-Monitoring/assets/167668407/03e81819-2229-40c7-a42d-dc8aceeadda6)

8.	Press Enter twice then type Signing Logs (Signing Logs is one of the Logs categories selected to be sent to the Log Analytics workspace)
9.	Click Run to run the Signing Logs query.
10.	The results of the query are populated in the Log Analytics workspace.
## Conclusion

The configuration process for ingesting Azure Active Directory logs into the Log Analytics workspace was completed successfully. As a result, these logs are now being efficiently collected and stored, ready for analysis. This configuration not only facilitates the monitoring of Azure tenant-level logs but also enables seamless integration with Microsoft Sentinel.
With the logs centralized in the Log Analytics workspace, organizations gain a holistic view of their Azure Active Directory activities. They can leverage the advanced capabilities of Microsoft Sentinel for enhanced threat detection and response. This integrated setup significantly improves the security and visibility of the Azure environment, empowering organizations to engage in proactive monitoring and streamline incident management processes.














