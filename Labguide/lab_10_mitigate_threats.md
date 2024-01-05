# Lab 10 - Mitigate threats using Microsoft 365 Defender

## Lab scenario

You're a Security Operations Analyst working at a company that implemented Microsoft Defender XDR solutions. You need to see the alerts in an incident to see the incident's full impact and do a root cause investigation and mitigate these alerts using M365 Defender tools.

## Lab objectives
 In this lab, you will perform the following in M365 Defender portal:
- Task 1: Create a Group
- Task 2: Apply Microsoft Defender for Office 365 preset security policies
- Task 3: Connect the Microsoft Defender for Cloud connector
- Task 4: Activate a Microsoft Security Rule
- Task 5: Manage Incidents
- Task 6: Investigate Alerts

## Architecture Diagram


### Task 1: Create a Group 

1. Sign in to the [Azure portal](https://portal.azure.com).

1. In the **Sign in** dialog box, copy and paste in the **Username** provided in the environment details page (odl_user_DID@xxxxx.onmicrosoft.com) and then select Next.

1. In the **Enter password** dialog box, copy and paste in the Password and then select **Sign in**.

1. On the **Stay signed in?** dialog box, select the Don’t show this again check box and then select **No**.

1. In the Search bar of the Azure portal, search and select **Azure Active Directory** or **Microsoft Entra ID**.

1. Select **Groups** and then click on **New group**.

1. Enter the below details for New group page :

   |Setting|Value|
    |---|---|
    |Group Type| **Microsoft 365** |
    |Group Name| **Sg-IT** |
    |Azure AD roles can be assigned to the group| **Yes** |

1. Click on **no owners selected** and select the **ODL_user** from the list and then click on **select**.

1. Click on **no members selected** and select the **ODL_user** from the list and then click on **select**.

   **Note**: Make sure you have selected **Group type** as Microsoft 365.

1. Select **Create** and click on **Yes**. 

### Task 2: Apply Microsoft Defender for Office 365 preset security policies

1. If you are not already at the Microsoft 365 Defender portal in your browser, go to (https://security.microsoft.com) and log in with the **Tenant Email** credentials.

1. From the navigation menu, under Email & Collaboration area, select **Policies & rules**(1) and select **Threat policies**(2).

   ![Lab overview.](./media/lab10-task3-threat-policies.png)

1. On the Threat policies dashboard, select **Preset Security Policies**.

   ![Lab overview.](./media/lab10-task3-preset-policies.png)

1. Under Standard protection, select **Manage protection settings**. Hint: If you see this option grayed out, refresh your browser using Ctrl+F5.

   ![Lab overview.](./media/lab10-task3-std-policies.png)

1. In the Apply Exchange Online Protection section, select **Specific recipients** and under **Domains** start writing your tenant’s domain name, select it, and then select **Next**.

   ![Lab overview.](./media/lab10-task3-std-policies01.png)

1. In the Apply Defender for Office 365 protection section, apply the same configuration as the previous step and select Next. Notice that this configuration applies policies for anti-phishing, Safe Attachments, Safe Links.

   ![Lab overview.](./media/lab10-task3-std-policies02.png)

1. In the Impersonation protection section, select **Next** four times (4x) to continue.

   ![Lab overview.](./media/lab10-task3-std-policies03.png)

1. In the Policy mode section, make sure the **Turn on the policy when finished** radio button is selected, and then select **Next**.

   ![Lab overview.](./media/lab10-task3-std-policies04.png)

1. Read the content under Review and confirm your changes and select **Confirm** to apply the changes and then select **Done** to finish.

   ![Lab overview.](./media/lab10-task3-std-policies05.png)

1. Under Strict protection, select **Manage protection settings**. Hint: Strict protection is found under “Email & Collaboration - Policies & rules - Threat policies - Preset security policies”.

   ![Lab overview.](./media/lab10-task3-strict-policies.png)

1. In the Apply Exchange Online Protection, select **Specific recipients** and under **Groups**, select your group, and then select **Next**. Notice that this configuration applies policies for anti-spam, outbound spam filter, anti-malware, anti-phishing.

   ![Lab overview.](./media/lab10-task3-strict-policies01.png)

1. In the Apply Defender for Office 365 protection section, apply the same configuration as the previous step and select Next. Notice that this configuration applies policies for anti-phishing, Safe Attachments, Safe Links.

   ![Lab overview.](./media/lab10-task3-strict-policies02.png)

1. In the Impersonation protection section, select **Next** four times (4x) to continue.

1. In the Policy mode section, make sure the **Turn on the policy when finished** radio button is selected, and then select **Next**.

   ![Lab overview.](./media/lab10-task3-strict-policies03.png)

1. Read the content under Review and confirm your changes and select **Confirm** to apply the changes and then select **Done** to finish.

   ![Lab overview.](./media/lab10-task3-strict-policies04.png)

### Task 3: Connect the Microsoft Defender for Cloud connector.

 In this task, you will connect the Microsoft Defender for Cloud connector.

 1. Navigate to Microsoft Sentinel, then on the left blade choose Configuration and select Data Connectors.  

 1. From the Data Connectors tab, search for the **Microsoft Defender for Cloud** connector and select it from the list.

 1. Select the **Open connector page** on the connector information blade.

 1. In the **Configuration** area, under Subscription, select the checkbox for the "Azure Pass - Sponsorship" subscription and slide the **Status** option to the right to indicate **Connected**.

1. The "Status" should be now *Connected* and "Bi-directional sync" should be *Enabled*.

1. Scroll down and under the "Create incidents - Recommended!" area, select **Enable**. This option creates an Analytics rule automatically for this service. You can manually add it later if not enabled here or change its configuration within the *Analytics* blade.

### Task 4: Activate a Microsoft Security Rule

In this task, you will activate a Microsoft Security rule.

1. In the Search bar of the Azure portal, type *Sentinel*, then select **Microsoft Sentinel**.

1. Select your Microsoft Sentinel Workspace you created in the previous labs.

1. Select **Analytics** from the Configuration area. By default, you will see the *Active rules*.

1. Select the **Create incidents based on Microsoft Defender for Cloud**.

   ![Lab overview.](./media/lab10-task4-analytics.png) 

 >**Note**: You can choose the existing **active rule** to edit or **create** new **active rule** and then edit them by selecting the respective rule in the active rules list.

5. After creating the active rule, select it for editing. On the right blade, click the **Edit** button. 

   ![Lab overview.](./media/lab10-task4-edit.png) 

1. Scroll down the page and under "Analytics rule logic - Filter by Severity", select the *Custom* drop-down list.

1. Unselect **Low** for the severity level and go back to the rule.

1. Select the **Next: Automated response** button and then select **Next: Review** button.

1. Review the changes made and select the **Save** button. The Analytics rule will be saved.

### Task 5: Manage Incidents

In this task, you will manage the incidents in M365 Defender portal.

1. If you are not already at the Microsoft 365 Defender portal in your Microsoft Edge browser, go to (https://security.microsoft.com). 

1. In the **Sign in** dialog box, copy and paste * Email/Username: <inject key="AzureAdUserEmail"></inject> and then select Next.

1. In the **Enter password** dialog box, copy and paste * Password: <inject key="AzureAdUserPassword"></inject> and then select **Sign in**.

1. From the sidebar menu, under **Incidents and Alerts**, select **Incidents**. Click on the incident **Multi-stage incident involving Execution & Discovery on one endpoint**.

1. To manage an incident, click on **Manage Incident** to edit the details of this incident.

   ![Lab overview.](./media/lab10-task1-manage.png) 

1. Here, you can edit the name of the incident, add tags, assign to an existing group or an user, change the status, classify the incident as required and even add comments.

   ![Lab overview.](./media/lab10-task1-manage01.png)

1. In the incident, the **Attack Story** tab provides a summary of the alerts and the incident graph on how these alerts are mapped.

   ![Lab overview.](./media/lab10-task1-attackstory.png)

1. You can further investigate these alerts by navigating to the **Alerts** tab.

   ![Lab overview.](./media/lab10-task1-alerts.png)

1. You can also see the devices and users affected by this incident in the **Assests** tab. You can verify that the affected device is **svm-xxxx** and the user is **demouser**.

   ![Lab overview.](./media/lab10-task1-assests.png)

1. The **Evidences & Responses** tab shows the initial evidences investigated by Microsoft Defender which includes the processes, IP addresses and registry values.

   ![Lab overview.](./media/lab10-task1-evidences.png)

1. The **Summary** tab gives us a summarized report of the incident including acitve alerts & their category, incident information, scope and much more.

   ![Lab overview.](./media/lab10-task1-summary.png)

### Task 6: Investigate Alerts

In this task you will investigate and mitigate the alerts through recommendations by Microsoft Defender.

1. In the Microsoft Defender portal, navigate to **Alerts** tab from the sidebar menu.

   ![Lab overview.](./media/lab10-task2-alerts.png)

1. You can click on any of these alerts to view the full details. Click on the alert named **Suspicious System Network Configuration Discovery**.

1. Click on **Maximize** to view the full alert details.

   ![Lab overview.](./media/lab10-task2-alerts-max.png)

1. Click on the dropdowm for the first suspicious behaviour to fully investigate the root cause for this activity.

   ![Lab overview.](./media/lab10-task2-alerts-max01.png)

1. You can see that this suspicious behaviour was reported when the user ran a certain command. 

   ![Lab overview.](./media/lab10-task2-alerts-max02.png)

1. Click on the ellipses and then select **Go Hunt**. This will redirect you to a new tab of **Advanced Hunting** where you can run the query and get the results.

   ![Lab overview.](./media/lab10-task2-alerts-hunt.png)

   ![Lab overview.](./media/lab10-task2-alerts-hunt01.png)

1. You can also investigate the alert further by navigating back the alerts and clicking on **Deep analysis**.

   ![Lab overview.](./media/lab10-task2-alerts-deep-analysis.png)

1. You will be redirected to a new tab. Click on **Submit** to get the detailed analayzed file.

   ![Lab overview.](./media/lab10-task2-alerts-deep-analysis01.png)

1. This process will take sometime, after which you can see the deep analysis of the alert and further investigate it.

   ![Lab overview.](./media/lab10-task2-alerts-deep-analysis02.png)

1. Microsoft Defender also provides recommendations to mitigate the alerts. On the alert details page, click on **Recommendations** tab to view all the recommendations.

   ![Lab overview.](./media/lab10-task2-alerts-recommendations.png)

## Review
In this lab, you have completed the following:
- Create a Group
- Apply Microsoft Defender for Office 365 preset security policies
- Connect the Microsoft Defender for Cloud connector
- Activate a Microsoft Security Rule
- Manage Incidents
- Investigate Alerts
