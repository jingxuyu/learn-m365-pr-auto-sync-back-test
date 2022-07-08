The Microsoft 365 Defender portal provides reports that allow you to monitor potential security threats in your organization. Even though threat security reports may not be directly related to Microsoft Teams, they can alert you to suspicious activity that's threatening the security of your organization.

## General security reports

Microsoft 365 Defender portal contains a dashboard that displays security trends and tracks the protection status of your identities, data, devices, apps, and infrastructure.

To view the report in the Microsoft 365 Defender portal, go to **Reports** > **Security report**.

- **Identities**: This category of reports provides data from Azure AD Risky Users report and Global Azure AD admin roles. Reports are related to Microsoft Teams because of sign-in activity to Microsoft Teams from different types of devices.  

- **Data**: This category of reports provides data from multiple sources, such as users with the most shared files, DLP policy matches, false positives and overrides. Reports are related to Teams because of data shared and accessed by Teams users.  

- **Devices**: This category of reports provides data from Microsoft Intune on devices at risk, device threat analytics, device compliance, malware on devices and users with malware detection. Reports are related to Microsoft Teams because of large numbers of mobile devices where Teams is installed.  

- **Apps**: This category of reports provides data from Microsoft Defender for Cloud Apps on threats from different apps, such as privileged OAuth apps, suspicious admin activity, impersonations, and cloud activity geographical locations. Reports are related to Microsoft Teams because of different apps that are integrated with Teams.

## Defender for Office 365 reports

Microsoft Defender for Office 365 contains a variety of security-related reports. To view the Defender for Office 365 reports, go to the **Microsoft 365 Defender portal** > **Reports** >  **Email & collaboration** > **Email & collaboration reports**, and select **View details** of the report. 


### Threat protection status report

The Threat protection status report is available in both EOP and Defender for Office 365; however, the reports contain different data. For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.

The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, zero-hour auto purge (ZAP), and Defender for Office 365 features like Safe Links, Safe Attachments, and impersonation protection features in anti-phishing policies. You can use this information to identify trends or determine whether organization policies need adjustment.

To view the report, go to **Reports** > **Email & collaboration reports**. On the **Email & collaboration reports** page, find **Threat protection status** and then select **View details**.

:::image type="content" source="../media/threat-protection-status.png" alt-text="Screenshot of Threat Protection Status report with information about detected files." lightbox="../media/threat-protection-status.png":::

In the **View data by Content** > **Malware** view, you can find the Malicious files detected in Microsoft Teams by filtering the workload. 

:::image type="content" source="../media/threat-protection-malware.png" alt-text="Screenshot of The Content malware view in the Threat protection status report." lightbox="../media/threat-protection-malware.png":::


### URL protection report

The URL protection report provides summary and trend views for threats detected and actions taken on URL clicks as part of Safe Links. This report will not have click data from users where the Safe Links policy was applied when the Track user clicks option is not selected.

To view the report, go to **Reports** > **Email & collaboration reports**. On the **Email & collaboration reports** page, find **URL protection report** and then select **View details**.

In the **View data by URL click by application** view, you can find the number of URL clicks by Teams by filtering the apps.

:::image type="content" source="../media/url-threat-protection-report-url-click-by-application-view.png" alt-text="[Screenshot of The URL click protection action view in the URL protection report." lightbox="../media/url-threat-protection-report-url-click-by-application-view.png" :::


