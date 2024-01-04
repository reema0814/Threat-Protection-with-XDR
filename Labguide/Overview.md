# Threat Protection with XDR

## Overview

Threat Protection with Extended Detection and Response (XDR) is a game-changing paradigm in cybersecurity, providing an unparalleled shield against modern threats. Unlike conventional security measures, XDR doesn’t just stop at surface-level defense; it orchestrates a symphony of security layers, unifying disparate tools and technologies to create an impenetrable fortress for an organization.

### Key features of Threat Protection with XDR

- Integration of Security Tools: XDR integrates multiple security tools and technologies such as endpoint security (EPP/EDR), network security, email security, cloud security, and more into a unified platform.
- Centralized Visibility and Analytics: XDR collects and aggregates data from diverse security sources, creating a comprehensive and unified view of the organization's security posture.
- Automated Threat Detection: XDR leverages its analytical capabilities to detect sophisticated threats, including zero-day exploits, malware, ransomware, phishing attacks, and other advanced threats that might evade traditional security measures.
- Contextualized Insights: XDR provides contextualized insights into detected threats, offering detailed information about the attack chain, affected systems, and the severity of the threat.
- Response and Remediation: When a threat is identified, XDR facilitates a swift response by automating threat containment, isolation, and remediation actions.

## Sandbox Scenario
Contoso is a global organization with a complex IT infrastructure that includes a combination of on-premises data centers and cloud-based resources. They are looking to enhance their security posture by deploying Azure Sentinel, Microsoft's cloud-native security information and event management (SIEM), and security orchestration automation and response (SOAR) solutions. Additionally, Contoso aims to onboard its cloud resources and servers to Azure Sentinel to gain better visibility and proactive threat detection and response capabilities.

By implementing a robust log analytics and threat detection program, Contoso aims to proactively identify and mitigate threats, reduce the risk of security breaches, and maintain a strong security posture in an ever-evolving threat landscape. This approach will enable Contoso to stay ahead of potential threats and protect its digital assets effectively.

## About the Sandbox

Using this environment, You'll be able to explore complete features and offerings offered by Microsoft Sentinel. Please find the detailed overview of the sandbox environment below.

### Pre-provisioned resources

#### **Virtual Machines**: 

- 2 *Windows Server 2019 Datacenter* Virtual machines, virtual machine-related resources like Virtual networks, Network security groups, managed disks, Network interface cards, and IP addresses are deployed as part of the automation.

  These virtual machines are tailored and configured to the sandbox's specifications. Files, applications, packages, and OS configurations are all pre-configured. It is recommended that you use the same virtual machine throughout the lab for the best experience.

#### **License and subscription**: 

- You'll have access to a pre-configured Microsoft user account with an active Azure subscription, a tenant, and a Microsoft 365 E5 license assigned to the user. 
   
  User account has assigned as Owner at subscription and Global administrator at the tenant level. You need to use the same user account throughout the lab to get the most out of the lab. 

#### **Azure Credits**: 

- You have been given a quota of **$83 USD** which includes the running cost of Pre-deployed resources, license cost, and other resources deployed while running through the lab.

  You will receive **cost alerts** to your registered email address at **50%/75%/90%/95%/100%** of the allowed Azure Credit is spent.

  You can visit the Azure Subscription page to check the current Azure credit spend and Analysis on the **Cost analysis** tab under the Cost Management option.

  ![Picture 1](./media/o1.jpg)

#### **Duration and Deletion of sandbox**:  

- The sandbox environment will be active for **30 days/730** hours from the time of registration. 
- The maximum allowed virtual machine uptime is only **40 hours**. It is recommended to deallocate the virtual machine when not in use.
- The virtual machine is set up with a custom feature called Idle start/stop. This custom package will check the virtual machine's idleness every **2 hours/120 minutes**. If the virtual machine is left idle for over 2 hours, a pop-up window will appear, prompting you to respond. If you do not take action within 10 minutes, the virtual machine will shut down automatically. This feature is enabled in virtual machines to optimize Azure costs.
- when 100% of Azure credits are spent, the sandbox environment will get automatically deleted without any prior notification. To retain the environment for a longer period and to get the most out of the environment, please follow the best practices mentioned below.

#### **Best practices**: 

- **Resources usage**: Please stop the virtual machines and other resources when not in use in order to minimize the Azure spend.

- **Azure Cost Analysis**: Maintain a practice of checking the Cost Analysis report of the assigned Azure subscription often in check the Azure spend so that the environment is for a longer duration of time.

- **Alert notifications**: Make sure to check your registered email's inbox for any alert-related emails. Alerts give you can head start to keep your Azure spending in control and to plan out the remaining credits in the best way possible.

## Lab guide Content:

You will have access to a lab guide which is a reference material to assist you in getting started with the exploration.

Based on your interests, you can use this lab guide as a reference to learn and test any XDR feature. You are also encouraged to explore additional features of XDR based on your interests and preferences.

- Lab 01 - Review and explore sentinel workspace
- Lab 02 - Create queries for Microsoft Sentinel using Kusto Query Language (KQL)
- Lab 03 - Understand Detection Modeling
- Lab 04 - Conduct attacks
- Lab 05 - Create Detections
- Lab 06 - Investigate an Incident
- Lab 07 - Create workbooks
- Lab 08 - Use Repositories in Microsoft Sentinel
- Lab 09 - Threat Hunting using Notebooks with Microsoft Sentinel
- Lab 10 - Mitigate threats using Microsoft Defender for Cloud
- Lab 11 - Integrate Logic App with Threat Protection and XDR

### Azure services and related products

- Log Analytics Workspace
- Microsoft Defender for Cloud
- Microsoft Defender for Endpoint
- Microsoft Entra ID
- Microsoft Sentinel
- Logic App
