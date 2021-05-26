The Advanced eDiscovery dashboard enables you to view reporting and eDiscovery data in a visual format. This is especially helpful when you have a large volume of documents and email messages that need to be reviewed. 

By creating widgets, you can quickly analyze your data to identify trends or key statistics that will help you develop your review strategy. The dashboard is customizable so you can add, remove, and configure widgets appropriate to your case and drill down into your content through the visuals.

For example, if your priority is to review all the data from a specific sender domain, you can create a widget that allows you to see that data with a bar chart, pie chart, column chart, or line chart. By applying a condition to the widget, you can filter the search even further. When finished, you can save the results as a query. 

Once you specify the sender domain, you can use this to create your search and save it as a query. 

### Create a widget on the review set dashboard
1. Open the case under investigation and navigate to the **Review Sets** tab, then select a review set.
1. In the **Individual results** dropdown list, click **Search profile view**.

     ![Search profile view screen](../media/search-profile-view.png) 

1. When the **Search profile view** page is displayed you will see several default widgets. 

     ![Search profile view widgets](../media/widgets.png) 

1. To customize the dashboard, **click New widget**. 

     ![Click New widget](../media/widgets.png) 

1. You can select **Choose from library** to add more widgets from a library.

     ![Choose from library to add more widgets from a library.](../media/add-library-widget.png) 

    Or you can click **Create custom widget** which displays a flyout page that you can use to set up a custom widget.

     ![Create custom widget screen.](../media/add-widget.png) 

1. In our example, we want to review the data from a specific sender domain and display the results in a bar chart. Therefore, after entering a name for the widget in the **Title** field, select **SenderDomain** from the **Choose pivot** drop-down list.
  
     ![Create custom widget example.](../media/senderdomain.png) 

1. Next, you would select **Bar chart**, then click **Add** to create the custom widget and display it on the **Search profile view** page.

     ![Create custom widget example, part 2.](../media/bar-chart.png) 

1. You can further filter your results by clicking the ellipses (…), then click **Apply condition**.

     ![Create custom widget example, part 3.](../media/apply-condition.png) 

    This condition enables you to select one or more sender domains to narrow your search results even further.

     ![Create custom widget example, part 4.](../media/apply-condition-2.png)   

    If necessary, you can narrow your search results even more by applying conditions to the other widgets on the dashboard. 

1. When you're done, click Save as query. 

     ![Create custom widget example, part 5.](../media/save-as-query.png) 

1. After you enter a name for your query, click **Save** and the search query that you saved is displayed under **Saved queries**.

     ![Create custom widget example, part 6.](../media/saved-queries.png) 

## Review data using source, text, and annotate views
Advanced eDiscovery displays content via several viewers each with different purposes. The various viewers can be used by clicking on any document within a review set. 

### Source view
The Source viewer displays the richest view of a document. It supports hundreds of file types and is meant to display the truest to native experience possible. For Microsoft Office files, the viewer uses the web version of Office apps to display content such as document comments, Excel formulas, hidden rows/columns, and PowerPoint notes.

 ![Source viewer.](../media/source-view.png) 

If the file is supported in Advanced eDiscovery, it will also be supported for text extraction, including Optical Character Recognition or OCR text extraction for image files, and will be viewable in the Source viewer and the Annotate viewer in Advanced eDiscovery. 

### Text view
The Text viewer provides a view of the extracted text of a file. It ignores any embedded images and formatting but is very effective if you are trying to understand the content quickly. Text view also includes these features:
- Line counter makes it easier to reference specific portions of a document
- Search hit highlighting that will highlight keywords within the document as well as the scrollbar
- Differential view provides a comparison view that highlights textual differences when viewing Near Duplicate documents

![Text viewer.](../media/text-view.png) 

![Text viewer.](../media/text-view-2.png)   
 
### Annotate view
The Annotate view provides features that allow users to apply markup on a document and is especially useful for redacting content in documents. Other features include the following:
- **Pencil**. Users can free-hand draw on a document to bring attention to certain portions of a document.
- **Select annotations**. Users can select annotations on a document to delete.
- **Toggle annotation transparency**. Users can create semi-transparent annotations to view the content behind the annotation.
- **Go to page**. Users can enter a specific page number to navigate to.
- **Zoom**. Users can set zoom level for annotate view.
- **Rotate**. Users can rotate document clockwise.
- **Search**. Users can search within a document and navigate to the various hits within the document.
 
![Annotate view.](../media/annotate-view-1.png) 
![Annotate view.](../media/annotate-view-2.png) 
 
### File metadata
The **File metadata** panel can be toggled on or off to display various metadata associated with the document. Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data. The File metadata panel allows a user to toggle on a view within the viewer.

 ![File metadata.](../media/file-metadata.png) 

## Query data in a review set
In most cases, it’s useful to dig deeper into the data in a review set and organize that data to facilitate a more efficient review. Using queries in a review set helps you focus on a subset of documents that meet the criteria of your review.

To create and run a query on the documents in a review set, click **New query** in the review set. 

 ![New query screen in a review set.](../media/new-query.png) 

After you name your query, you can create it by using a combination of conditions and query language in the Keywords condition card. You can also group conditions together as a block (called a **condition group**) to build a more complex query. For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery?azure-portal=true).

 ![Condition group in building a query.](../media/new-query-2.png) 

In addition to queries that you can save, you can use filters to quickly apply additional conditions to a review set query. This helps you further refine the results displayed by a review set query.

 ![Using filters in building a query.](../media/filters.png) 

> [!NOTE]
> There are two major differences between filters and queries:
> - Filters cannot be saved as part of the query and do not persist beyond the existing session. 
> - Filters are applied in addition to the current review set query. Applying a different query will replace the results returned by the current query.

## Tag documents in a review set
When compliance officers, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags. For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "Non-responsive". After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "Non-responsive" which removes this content from the next steps in the Advanced eDiscovery workflow. 

 ![Manage tags screen in review set](../media/manage-tags.png) 

When you click **Manage tags**, a customizable coding panel is displayed to enable you to effectively apply tags and triage and organize the content under review.

 ![Applying tags.](../media/tagging-pane.png) 

When viewing a single document in a review set, you can display the tags that a reviewer can use by clicking **Tagging panel**. This will enable you to apply tags to the document displayed in the viewer. Bulk tagging is commonly used by organizations to significantly reduce review time so that investigations are more cost effective and can be accomplished by selecting multiple files and then using the tags in the **Tagging panel** like tagging single documents. Bulk untagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files. 

## Attorney-client privilege detection using machine learning
Advanced eDiscovery recently introduced a new smart tag for detecting attorney-client privileged communications. The smart tag capability leverages a pre-trained machine learning (ML) model that analyzes documents and lets you instantly search, identify, and tag potentially privileged documents.

To take full advantage of the attorney-client privilege detection model, it is recommended that you submit a list of attorneys for your organization when you set up attorney-client privilege detection in your tenant. The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant. The ML model also uses machine learning to determine the likelihood that the document contains content that is legal in nature. The analysis of this combination produces three properties for each document which ultimately determines whether or not privileged communications were detected:
 - **AttorneyClientPrivilegeScore**. The likelihood the document is legal in nature; the values for the score are between **0** and **1**.
 - **HasAttorney**. This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**. The value is also set to **false** if your organization didn't upload an attorney list.
 - **IsPrivilege**. This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.
 
These properties and their corresponding values are searchable within a review set and added to the file metadata of the documents in a review set, as illustrated in the screenshot below:

 ![Attorney-client privilege score.](../media/attorney-client-privilege-score.png) 

### Set up attorney-client privilege detection
1. To enable attorney-client privilege detection in your tenant, navigate to the **Cases** tab in Advanced eDiscovery and click **Configure global analytics settings**.
 
    ![Setting uyp Configure global analytics settings, part 1.](../media/advanced-ediscovery.png) 

1. On the **Analytics settings** tab, click **Manage attorney-client privilege setting**.
1. On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.

    ![Setting uyp Configure global analytics settings, part 2.](../media/attorney-client-privilege.png) 

### Upload a list of attorneys (optional)
To take full advantage the privilege detection model, you need to upload a list of email addresses for the lawyers and legal personnel who work for your organization.
1. Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line. Save this file to your local computer.
1. Navigate to the **Cases** tab in Advanced eDiscovery and click **Configure global analytics settings**. 
1. On the **Analytics settings** tab, click **Manage attorney-client privilege setting**.
1. On the **Attorney-client privilege** flyout page, click **Choose File** and then find and select the .csv file that you created in step 1.
1. Click **Save** to upload the attorney list.

### Use the attorney-client privilege detection smart tag
After attorney-client privilege detection has been enabled, you will see an enhanced view of the **Tagging panel** which displays **Attorney-client privilege** settings as illustrated below:

 ![Attorney-client privilege Tagging panel.](../media/tagging-panel.png) 

One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group. A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group. This lets you quickly identify documents that are potentially privileged during a document review. Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged. 

There are two locations that enable you to configure smart tag groups:
- In the review set, click **Manage review set** and then click **Manage tags**.
- In the **Tagging panel**, click **Manage tags**. 

Either method will open the interface that enables you to customize the Attorney-client privilege options and settings. 

 ![Two locations for configuring smart tag groups.](../media/manage-tags-attorney-client-privilege.png) 

For more information, see [Use the attorney-client privilege detection model](/microsoft-365/compliance/attorney-privilege-detection?azure-portal=true).
