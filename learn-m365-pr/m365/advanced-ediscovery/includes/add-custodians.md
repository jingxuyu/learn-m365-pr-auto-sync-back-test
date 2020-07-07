This section describes how Advanced eDiscovery supports the first two phases of the EDRM model – Identification and Preservation. 
 
![First two phases of the EDRM model – Identification and Preservation.](../media/edrm-model.png) 

The first phase in the EDRM model is *Identification*. This phase involves identifying the people in the organization who are in possession of documents and communications relevant to the investigation. These individuals are the custodians of data, or just custodians, and are defined as "persons having control of a document or electronic file". For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message. 

Once the custodians have been identified, they are added to an Advanced eDiscovery case. Creating a case is accomplished by navigating to the **Advanced eDiscovery** home page in the Microsoft 365 Compliance Center, navigating to the **Cases** tab, then clicking **Create a case**. 
 
![Advanced eDiscovery home page in the Microsoft 365 Compliance Center.](../media/advanced-ediscovery.png) 

Once the case has been created, you can begin adding the persons of interest by navigating to the **Custodians** tab and clicking **Add custodians**.

![Custodians tab in Advanced eDiscovery home page in the Microsoft 365 Compliance Center.](../media/add-custodians.png) 

When you add a custodian, the system automatically identifies and places a hold on their Exchange mailbox and OneDrive for Business account. This is the *Preservation* phase of the EDRM model. During this process, you can also select additional data sources such as SharePoint sites, Teams, and Yammer groups that the custodian either contributed to or is a member of. 

> [!NOTE]
> All Yammer networks are required to be in [Native Mode](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode?azure-portal=true) for Yammer content to be discovered in eDiscovery. 

 ![Selecting additional locations ](../media/select-additional-locations.png) 

The final step when adding a custodian to a case is to place the custodian on hold. When you place a custodian on hold, all the content from the locations you’ve selected that are associated with the custodian is preserved until you remove the hold or release the custodian from the case. 

## Create holds to preserve content
When custodians are placed on hold, the users and their selected data sources are automatically added to a custodian hold policy. Hold policies can be viewed and modified by navigating to the **Holds** tab in the case.

 ![Hold policies can be viewed and modified by navigating to the Holds tab in the case.](../media/create-holds.png) 

Holds enable organizations to immutably preserve mailbox items and documents for discovery and other compliance needs by keeping those items within the infrastructures of Exchange and SharePoint. Data is preserved in a way that is tamper-proof and discoverable.

### Place Exchange Online mailboxes on hold
Exchange Online uses the Recoverable Items folder to immutably preserve mailbox content, be it edits, deletions, metadata, or folder hierarchy. The Recoverable Items folder is a hidden folder which is not visible in Outlook, Outlook on the web, or other mail clients. The folder contains several subfolders which are also hidden from users that immutably preserve data when a mailbox is placed on hold:
- **Deletions**. This subfolder contains all items that are deleted from the Deleted Items folder in the mail client.
- **Versions**. If a hold is enabled, this subfolder contains the original and modified copies of the deleted items. 
- **Purges**. If a hold is enabled, this subfolder contains all items that are purged. 
- **Discovery Holds**. If a hold is enabled, this subfolder contains all items that meet the hold query parameters and are purged.
- **Calendar Logging**. This subfolder contains calendar changes that occur within a mailbox.

### Place SharePoint Online sites on hold
When you place a SharePoint Online site on hold, the content in that site remains in its original location. Users can continue to work with their documents, but a copy of the content as it was when you initiated the hold is preserved. In addition to existing content, any new content that is created or added to the site after it was put on hold will be preserved if the content is deleted. 

Holds are applied at the site level. When you place a site on hold, a Preservation Hold library is created, if one does not already exist. Most users cannot view the Preservation Hold library because it is only visible to site collection owners. If a person attempts to change or delete content in a site that is on hold, the hold policy first checks whether the content has been changed since the hold was applied. If this is the first change since the hold was applied, the hold policy copies the content to the Preservation Hold library and then allows the person to change or delete the original content. 
  
 ![Process for placing SharePoint Online sites on hold.](../media/sharepoint-holds-1.png) 

### Place a hold on Microsoft Teams 
Channel conversations that are part of a Microsoft Teams channel are stored in the mailbox that is associated with the Team. On the other hand, files that team members share in a channel are stored on the Microsoft Teams associated SharePoint site. Therefore, if you need to retain conversations and files in a channel you must place the Microsoft Team mailbox and SharePoint site on hold by adding Teams content to the custodial hold. Consider the following example:

 ![Example of placing a hold on Microsoft Teams](../media/choose-teams.png) 
 
When you click **Choose teams** (then click **Choose teams** again on the flyout page) a list of Microsoft Teams that the custodian is currently a member of will be displayed. 

 ![Choose teams flyout page](../media/flyout-page.png) 

When you select the Team (or Teams) associated with the custodian, the system will automatically identify and select 
the associated SharePoint site and mailbox associated with that Microsoft Team. 

Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the users who participate in the chat. Files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you must place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list.

Every Microsoft Team or team channel contains a Wiki for note taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.

## What is a hold notification?
An organization is required to preserve relevant information when it learns about an impending litigation or regulatory investigation. Since the process of adding a custodian to a case and placing holds on their content is transparent to the end user, the organization should inform the user about the hold and their duty to preserve relevant information. 

The custodian communications tool enables legal teams to configure the following notifications:
1.	**Issuance notice**. A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter. This notice instructs the custodians to preserve any information that may be needed for discovery.
1.	**Re-Issuance notice**. During a case, custodians may be required to preserve additional content (or less content) than was previously requested. For this scenario, you can update the existing hold notice and reissue it to custodians.
1.	**Release notice**. Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case. Additionally, you can notify the custodian that they are no longer required to preserve content and provide instructions about how to resume their normal work activity with regard to their data.
1.	**Reminders and escalations**. In some instances, just issuing a notice isn’t enough to satisfy legal discovery requirements. With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.
    - **Reminders**: After a legal hold notice has been issued or reissued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.
    - **Escalations**: In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.

## Create a hold notification
Using the Communications tool, legal teams can systematically send, collect, and track hold notifications. The tool enables teams to customize the hold notification workflow and the content in the notices sent to custodians.

The first step to create a hold notification is to open the case in question and navigate to the **Communications** tab, then click **New communication**.

 ![Step 1 to create a hold notification is to open the case in question and navigate to the Communications tab, then click New communication.](../media/new-communication.png) 

The next step is to enter a descriptive name and select the Issuing Officer on the **Name communication** page.

 ![Step 2 is to enter a descriptive name and select the Issuing Officer on the Name communication page.](../media/name-communication.png) 

After clicking **Next**, you can use the rich text editor to create the Hold Notice and variables such as display name are available that can be used to create the notice. 

 ![Step 3 is using the rich text editor to create the Hold Notice and variables such as display name are available that can be used to create the notice.](../media/define-portal-content.png) 

On the **Set Notifications – Required** page, you can define if this is a new issuance, reissue or release of hold for the communication and define the content within the hold as well as utilize common variables such as display name, acknowledgment link and more.

 ![Set Notifications - Required page](../media/set-notifications.png) 

On the **Set Notifications – Optional** page, you have the ability to create reminders and escalation notifications and add links to ensure that custodians acknowledge receiving this information. Since Advanced eDiscovery is integrated with Azure Active Directory, you can even escalate the notification to the custodian’s manager to remind the custodian to take action. 

After selecting the custodians you want to notify, you can review your settings, then choose to select either **Send** or **Cancel**.

In turn, custodians receiving hold notifications will receive something like the sample below and are able to acknowledge receipt of the notice by clicking one of the three buttons near the bottom of the message:

 ![Issuance of hold notification](../media/issuance-hold-notification.png) 

## Manage custodian details
After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory (Azure AD) and are viewable in the case.

To view the details, click the custodian from the list on the **Custodians** tab. A flyout page like the one below is displayed which contains details about the custodian and the types of data on hold.

 ![View details by clicking the custodian from the list.](../media/update-index.png) 

The flyout page also enables you to do the following:
- **Edit a custodian**. As the case progresses, you may discover that there may be additional data sources relevant to a specific custodian. Alternatively, you may want to remove certain data sources that have been reviewed and deemed as not relevant. Clicking the **Edit** button next to **Data sources** lets you add or remove data sources.

  ![Click the Edit button to add or remove data sources.](../media/data-sources.png)  

- **Re-index custodian data**. During the lifetime of a case, new data sources might be associated with a custodian while some data remains partially indexed. Clicking **Update index** lets you re-index the custodian's data, remediate any partially indexed items and update the index for the custodian's data. 
- **View custodian audit activity**. Clicking **View custodian activity** lets you search the audit log for activities performed by a custodian, such as when they viewed a specific document or purged an item from their mailbox.
- **Release the custodian from the case**. Custodians are automatically released when a case is closed. In other scenarios, you can click **Release custodians** when the custodian is no longer under obligation to preserve content for a case, or when the custodian is no longer considered to be relevant to the case.

## View custodian activities in the audit log
The Custodian activities search page is displayed when you click **View custodian activity**. You can select different custodians in the **Custodian** drop-down box, but you can only search for activities for one custodian at a time.

 ![Custodian activities search page  ](../media/custodian-activities.png) 

Next, click the **Activities** drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. 

 ![Activities drop down list ](../media/activities.png) 

The last step is to select a date and time range to display the events that occurred within that period. Note, the last seven days are selected by default and the maximum date range that you can specify is one year.

The results of an audit log search are displayed under **Results** on the **Custodian activities** page as illustrated below:

![The results of an audit log search are displayed under Results on the Custodian activities page.](../media/custodian-activities.png)  

The results contain the following information about each event returned by the search.
- **Date**: The date and time (in UTC format) when the event occurred.
- **IP address**: The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format.
- **User**: The user (or service account) who performed the action that triggered the event.
- **Activity**: The activity performed by the user. This value corresponds to the activities that you selected in the Activities drop down list. For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.
- **Item**: The object that was created or modified as a result of the corresponding activity. For example, the file that was viewed or modified or the user account that was updated. Not all activities have a value in this column.
- **Detail**: Additional detail about an activity. Again, not all activities will have a value.

You can filter the results by date, IP address, activity, or by a specific item. To filter the search results, click **Filter results**, then click one of the boxes under a column header and type a word or phrase, depending on the column you are filtering on. The results will dynamically readjust to display the events that match your filter.

The **Export results** button lets you export the results of an audit log search to a comma-separated value (CSV) file on your computer. This enables you to open the file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.

## Learn more
 - [Overview of Native Mode](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode?azure-portal=true)
