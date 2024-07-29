# Lab 05 - Investigate an Incident

## Lab scenario

You are a Security Operations Analyst working at a company that implemented Microsoft Sentinel. You already created Scheduled and Microsoft Security Analytics rules. The Fusion and Anomalies Analytics rules are also enabled in your environment. Now is the time to investigate the Incidents created by them.

An incident can include multiple alerts. It is an aggregation of all the relevant evidence for a specific investigation. The properties related to the alerts, such as severity and status, are set at the incident level. After you let Microsoft Sentinel know what kinds of threats you are looking for and how to find them, you can monitor detected threats by investigating incidents.

## Lab objectives
 In this lab, you will understand the following:
 - Task 1: Investigate an incident

## Estimated timing: 20 minutes

## Architecture Diagram

  ![Lab overview.](./media/SC-200ex8.1.png)

### Task 1: Investigate an incident

In this task, you will investigate an incident.

1. Select the Microsoft Sentinel Workspace you created earlier.

1. Select the **Incidents** page under Threat management from left side blade and Review the list of incidents

   ![](./media/7-1.png)

    >**Note:** The Analytics rules are generating alerts and incidents on the same specific log entry. Remember that this was done in the *Query scheduling* configuration to generate more alerts and incidents to be utilized in the lab.
  
1. Select one of the **Startup RegKey (1)** incidents. click on the **<< (2)** icon appear on the right side.Review the incident details on the right blade that opened. Scroll down and select the **View full details (3)** button.

   ![](./media/7-2.png)

1. If the New incident experience pop-up appears, follow the prompts by reading the information by selecting the **Next** button.

1. On the left blade of the incident, change the Status to **Active** and then select **Apply**.

    ![Lab overview.](./media/Lab07-task01-activestatus.png)

1. Scroll down to the *Tags* area, select **+ (1)** and type **RegKey (2)** and select **OK (3)**.

     ![Lab overview.](./media/7-3.png)

1. Scroll down and in the *Write a comment...* box type: *I will research this* and select the **>** icon to submit the new comment.

    ![Lab overview.](./media/comment.png)

1. Hide the left blade by selecting the **<<** icon next to the owner.

1. Review the **Incident timeline** window. For the *Startup RegKey* alert, select the ellipsis **(...) (1)** icon and then **Run playbook (2)**. You will see the *Alert playbooks*. This option helps you to run playbooks manually.

    ![Lab overview.](./media/7-4.png)

    >**Note**: If you did not see any playbook no need to worry there might be the case where sentinel does not reflect the playbook, we can proceed with the next step

1. Close the *Alert playbooks* blade by selecting the **x** icon in the top right.

1. Review the **Entities** window. At least the *Host* entity that we mapped within the KQL query from the previous exercise should appear. **Hint:** If no entities are shown, refresh the page.

   ![Lab overview.](./media/7-5.png)

1. Select the **Tasks** button from the command bar.

   ![Lab overview.](./media/7-6.png)

1. Select **+ Add task (1)**, type **Review who owns the machine (2)** in the Title box and select **Save (3)**.

   ![Lab overview.](./media/7-7.png)

1. Close the *Incident tasks* blade by selecting the **x** icon in the top right.

   ![Lab overview.](./media/7-8.png)

1. Select the new **Activity Log** button from the command bar. Review the actions you have taken during this exercise. Close the *Incident activity log* blade by selecting the **x** icon in the top right.

   ![Lab overview.](./media/7-9.png)

1. From the almost hidden left blade, select the user icon named **Unassigned (1)**. The new incident experience allows quick changes from here.

1. Select **Assign to me (2)** and then scroll down to select **Apply (3)** to save the changes.

    ![Lab overview.](./media/assignedtome.png)

1. Select the **Investigate** button.

    ![Lab overview.](./media/7-10.png)

1. **Hover** the svm-server entity icon and wait for new *exploration queries* to be shown. It looks like *Related Alerts* has more data on it. Select the name of the exploration query **Related Alerts** to bring them to the investigation graph or select **Events >** to investigate them with a KQL query.

    ![Lab overview.](./media/Lab07-task01-investigationpicture.png)

   >**Hint:** If the icons are too small for your screen, select **(+)** to magnify them.   

1. Close the query window by selecting the **X** icon at the top right to go back to the *Investigation* page.

1. Now select the **svm-server** entity, a window on the right opens for more detailed information. Review the **Info** page.

   ![Lab overview.](./media/7-11.png)

1. Select **Timeline** button. Hover the incidents and see which things on the graph occurred at what point in time.

   ![Lab overview.](./media/7-12.png)

1. Close the investigation graph by selecting the **X** icon at the top right of the page.

1. Back in the incident page, in the left pane select **Active Status (1)** and select **Closed (2)**. In the *Select classification* drop-down review the different options. After that, select **True positive - suspicious activity (3)** and then select **Apply (4)**.

   ![Lab overview.](./media/7-13.png)

## Review
In this lab, you have completed the following tasks:
- You have investigated an incident.
