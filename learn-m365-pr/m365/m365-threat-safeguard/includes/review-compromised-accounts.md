Microsoft Defender for Identity security alerts explain suspicious activities detected by Microsoft Defender for Identity sensors on your network, and the actors and computers involved in each threat. Alert evidence lists contain direct links to the involved users and computers, to help make your investigations easy and direct.

Microsoft Defender for Identity security alerts are divided into the following categories or phases, like the phases seen in a typical cyber-attack kill chain:

- Reconnaissance phase alerts
- Compromised credential phase alerts
- Lateral movement phase alerts
- Domain dominance phase alerts
- Exfiltration phase alerts

Each Microsoft Defender for Identity security alert includes:

- **Alert title.** Official Microsoft Defender for Identity name of the alert.
- **Description.** Brief explanation of what happened.
- **Evidence.** Additional relevant information and related data about what happened to help in the investigation process.
- **Excel download.** Detailed Excel download report for analysis

:::image type="content" source="../media/security-alert.png" alt-text="Microsoft Defender for Identity security alert." border="false":::

Alerts can also be viewed within Microsoft Defender for Cloud Apps:

:::image type="content" source="../media/cloud-app-security-alerts.png" alt-text="Microsoft Defender for Cloud Apps alert." lightbox="../media/cloud-app-security-alerts-magnify.png" border="false":::

The following scenario describes an investigation into an attacker gaining administrator access to the domain controller and compromising the Active Directory domain and forest.

The first alert we notice in the Defender for Cloud Apps portal shows **User and IP address reconnaissance** (SMB). Clicking into this alert, we see (under Description) that a user was able to learn the IP addresses of two accounts by enumerating SMB sessions on the domain controller.

:::image type="content" source="../media/user-ip-address-reconnaissance.png" alt-text="User and I P address reconnaissance." lightbox="../media/user-ip-address-reconnaissance-magnify.png" border="false":::

Within the alert, we can also find the activity log, which shows more information about the command that was run.

:::image type="content" source="../media/activity-log.png" alt-text="Activity log." lightbox="../media/activity-log-magnify.png" border="false":::

Back in the Alerts overview, we can see a more recent alert pointing to an **overpass-the-hash attack**.

:::image type="content" source="../media/overpass-hash-attack.png" alt-text="Alert: Overpass-the-hash-attack." lightbox="../media/overpass-hash-attack-magnify.png" border="false":::

Opening the suspected overpass-the-hash-attack (Kerberos) alert, we see evidence that the user account was part of a lateral movement path.

:::image type="content" source="../media/open-suspected-attack.png" alt-text="Open the suspected attack alert." lightbox="../media/open-suspected-attack-magnify.png" border="false":::

The next alert shows a **Suspected identity theft (pass-the-ticket)**.

:::image type="content" source="../media/pass-ticket-alert.png" alt-text="Pass-the-ticket alert." lightbox="../media/pass-ticket-alert-magnify.png" border="false":::

Microsoft Defender for Identity has detected theft of a ticket from a domain administrator to the infiltrated PC. The Defender for Cloud Apps portal shows exactly which resources were accessed using the stolen tickets.

:::image type="content" source="../media/alert-pass-ticket.png" alt-text="More information on the pass-the-ticket alert." lightbox="../media/alert-pass-ticket-magnify.png" border="false":::

In the next alert, we see that the stolen credentials were used to run a remote command on the domain controller.

:::image type="content" source="../media/alert-remote-code-execution.png" alt-text="Alert showing remote code execution attemptl." lightbox="../media/alert-remote-code-execution-magnify.png" border="false":::

Looking into the Activity Log for the alert, we see that the command was to create a new user within the Administrators group.

:::image type="content" source="../media/create-new-user.png" alt-text="Command used to create a new user." lightbox="../media/create-new-user-magnify.png" border="false":::

From all the previous alerts, we suspect that an attacker has:

- Infiltrated a PC.
- Used the PC to determine IP addresses of other users' PCs, one of which belongs to a domain administrator.
- Performed an overpass-the-hash attack by stealing the NTLM hash from another user who previously authenticated to the infiltrated PC to access any resource the user has permissions for. (In this case, local admin rights to IP addresses previously exposed)
- Used the newly stolen credentials to gain access to the domain administrator's PC.
- Used their access to the domain administrator's PC to steal the identity of the domain administrator.
- Used the domain administrator's identity to access the domain controller, and created a new user account with domain administrative permissions.

With domain administrative permissions, the attacker has effectively compromised the environment. Now they are free to perform any number of attacks, such as a Skeleton Key attack.

### Explore how to investigate and respond to attacks with Microsoft Defender for Identity

View a [video version](https://www.microsoft.com/videoplayer/embed/RE4GiZJ) of the interactive guide (captions available in more languages).

[:::image type="content" source="../media/investigate-respond.png" alt-text="Microsoft Defender for Identity." border="false":::](https://mslearn.cloudguides.com/guides/Investigate%20and%20respond%20to%20attacks%20with%20Microsoft%20Defender%20for%20Identity)  

Be sure to click the full-screen option in the video player. When you're done, use the **Back** arrow in your browser to come back to this page.
