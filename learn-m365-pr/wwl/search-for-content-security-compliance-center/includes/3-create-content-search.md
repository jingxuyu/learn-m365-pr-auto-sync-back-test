Organizations can use the Content search eDiscovery tool in the c to search for in-place content, such as:

 -  email
 -  documents
 -  instant messaging conversations

This tool can be used to search for content in the following cloud-based Microsoft 365 data sources:

 -  Exchange Online mailboxes
 -  SharePoint Online sites
 -  OneDrive for Business accounts
 -  Microsoft Teams
 -  Microsoft 365 Groups
 -  Yammer Groups

> [!NOTE]
> In an Exchange hybrid deployment, you can't use the Content search tool to search emails in on-premises mailboxes. You can only use the tool to search cloud-based mailboxes. In an Exchange hybrid deployment, you can search for Teams chat data in on-premises mailboxes.

After you run a search, the number of content locations and an estimated number of search results are displayed on the search flyout page. You can quickly view statistics, such as the content locations that have the most items that match the search query. After you run a search, you can preview the results or export them to a local computer.

Most organizations typically limit access to the Content search tool in the Microsoft Purview compliance portal to an administrator, compliance officer, or eDiscovery manager. These individuals must be a member of the eDiscovery Manager role group in the compliance portal.

### Create and run a search

You should complete the following steps to create and then run a content search:

1.  In the **Microsoft Purview compliance** portal, select **Content search** in the navigation pane.
2.  On the **Content search** page, select **+New search** on the menu bar. This action initiates the **New search** wizard.
3.  In the **New search** wizard, on the **Name and description** page, enter a name for the search and an optional description that helps identify the search. The name of the search must be unique in your organization. Select **Next**.
4.  On the **Locations** page, choose the content locations that you want to search. You can search mailboxes, sites, and public folders. :::image type="content" source="../media/new-search-wizard-locations-page-067651ea.png" alt-text="Screenshot of the Locations page in the New Search wizard.":::
    
     -  **Exchange mailboxes**. Set the toggle to **On** and then under the **Included** column, select **Choose users, groups, or teams** to specify the mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups. You can also search the mailbox associated with a Microsoft Team (for channel messages), Office 365 Group, and Yammer Group. For more information about the application data stored in mailboxes, see [Content stored in mailboxes for eDiscovery](/microsoft-365/compliance/what-is-stored-in-exo-mailbox?azure-portal=true).
     -  **SharePoint sites**. This location applies to both SharePoint sites and OneDrive accounts. Set the toggle to **On** and then under the **Included** column, select **Choose sites** to specify SharePoint sites and OneDrive accounts to place on hold. Enter the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for a Microsoft Team, Office 365 Group, or Yammer Group.
     -  **Exchange public folders**. Set the toggle to On to put all public folders in your Exchange Online organization on hold. You can't choose specific public folders to put on hold. Leave the toggle switch off if you don't want to put a hold on public folders.
     -  **Add App Content for On-Premises Users**. Keep this check box selected to search for Teams content for on-premises users. For example, if you search all Exchange mailboxes in the organization and this check box is selected, the cloud-based storage used to store Teams chat data for on-premises users will be included in the scope of the search. For more information, see [Search for Teams chat data for on-premises users](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users?azure-portal=true).
5.  On the **Define your search conditions** page, select one of the following options to create your search query:
     -  **Condition card builder**. This option enables you to build your query by entering keywords and adding conditions.
     -  **KQL editor**. This option replaces the keywords and conditions with a text box for typing in the actual Keyword Query Language (KQL) code for your search query.
    
    :::image type="content" source="../media/new-search-wizard-conditions-page-af4b0e83.png" alt-text="Screenshot of the Define your search conditions page in the New Search wizard.":::
    
    
    If you select the **Condition card builder** option, keep in mind the following criteria:
    
    
     -  You must specify conditions such as:
         -  Keywords.
         -  Message properties, such as sent and received dates.
         -  Document properties, such as file names or the date that a document was last changed.
     -  You can use more complex queries that use a Boolean operator, such as AND, OR, NOT, and NEAR.
     -  If you leave the keyword box empty, all content located in the specified content locations is included in the search results. For more information, see [Keyword queries and search conditions for eDiscovery](/microsoft-365/compliance/keyword-queries-and-search-conditions?azure-portal=true).
     -  If you select the **Show keyword list** checkbox and then type a keyword in each row, the keywords on each row are connected by a logical operator (c:s) that's similar in functionality to the OR operator in the search query that's created. Why use the keyword list? You can get statistics that show how many items match each keyword. By doing so, you can quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about the keyword list and search statistics, see [Get keyword statistics for searches](/microsoft-365/compliance/view-keyword-statistics-for-content-search?azure-portal=true).
        
            > [!NOTE]
            > To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.
     -  You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that's created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (c:c) that's similar in functionality to the AND operator. That means that items must satisfy both the keyword query and one or more conditions to be included in the results. This process is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see [Search conditions](/microsoft-365/compliance/keyword-queries-and-search-conditions?azure-portal=true).
6.  Review the search settings (and edit if necessary), and then submit the search to start it.

To access this content search again, or to access other content searches listed on the **Content search** page, select the search and then select **Open**.
