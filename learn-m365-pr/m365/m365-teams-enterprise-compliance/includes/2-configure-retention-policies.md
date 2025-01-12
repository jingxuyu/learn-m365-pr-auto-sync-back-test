Accidental or intentional deletion of content is a problem for compliance because you often must ensure that content is kept for minimum periods.

Suppose your legal firm needs to ensure that you keep all information that relates to a case indefinitely but information about children must be deleted two years after their case has been resolved. You need to ensure the controls you have in Microsoft Teams can automatically enforce these and other legal requirements.  

Here, you'll learn about retention policies and Data Loss Prevention (DLP) policies and how they can be used to keep or delete Teams content such as chat items or files.

## Retention policies

In Microsoft Teams, retention policies allow you to keep data that's important and remove data that's no longer relevant.
You may want to set a retention policy for regulatory, legal, business, or other reasons. You use retention policies to remove content and communications that are no longer needed or keep data for a certain period of time and then delete it.

### Create a retention policy for Microsoft Teams

By default, Teams chat, channel, and files data are retained indefinitely. Use Teams retention policies for chat and channel messages and decide proactively whether to retain the data, delete it, or retain it for a specific period.

To create a retention policy:

1. Sign into the [Microsoft Purview compliance portal](https://compliance.microsoft.com), from the left navigation, select **Data Lifecycle Management** under **Solutions**..
1. On the **Data Lifecycle Management** page, select the **Retention policies** tab.
1. Select **+ New retention policy** to create a new retention policy.

    :::image type="content" source="../media/create-new-retention-policies.png" alt-text="Screenshot of the Microsoft Purview compliance portal, showing the Data Lifecycle Management page, highlighting the retention policies tab, with the + New retention button highlighted." lightbox="../media/create-new-retention-policies.png":::

1. On the **Name your policy** page, enter a **name** and optionally a **description**. Then select **Next**.
1. On the **Choose the type of retention policy to create​** page, specify the kind of policy, either **Adaptive** or **Static**, then select **Next**.
1. On the **Choose locations to apply the policy** page, make your selections, and then select **Next**.
1. On the **Decide if you want to retain content, delete it, or both** page, select your retention period, and then select **Next**.
1. On the **Review and finish** page, check that your settings are correct, and then select **Submit**.

## DLP policies

DLP helps you to comply with your region's data protection regulations and industry standards by identifying and protecting sensitive information. Sensitive information can include financial data or personal information such as credit card numbers, social security numbers, or health records. With a DLP policy you can identify, monitor, and automatically protect sensitive information.

A DLP policy defines the locations of content to protect, including Microsoft Teams chat and channel messages, Exchange Online, SharePoint Online, and OneDrive for Business sites. It also defines how to protect the content using rules. For example, a rule might be configured to look for content containing social security numbers that have been shared with people outside your organization.

In Microsoft Teams, you can define policies to prevent people from sharing sensitive information in a Teams channel or chat session. You can select from either a custom policy or use a template. If you create a DLP policy using a template, you can amend the settings to suit your needs. If you create a DLP policy using the custom option, you define the policy rules.

To create a new DLP policy using a template:

1. Sign into the [Microsoft Purview compliance portal](https://compliance.microsoft.com), from the left navigation, select **Data loss prevention** under **Solutions**.
1. On the **Data loss prevention** page, select the **Policies** tab.
1. Select **+ Create policy** to create a policy.

    :::image type="content" source="../media/create-new-data-loss-prevention-policies.png" alt-text="Screenshot of the Microsoft Purview compliance portal, showing the data loss prevention page, highlighting the policies tab, with the + create policy button highlighted." lightbox="../media/create-new-data-loss-prevention-policies.png":::

1. On the **Start with a template or create custom policy** page, select either a **country or region** to display the available **Categories** and **Templates**. Or select *Search for specific templates*. Then select **Next**.
1. The DLP wizard steps through the settings on each page, allowing you to make your selections. Select **Next** to move to the next page.
1. On the **Choose locations to apply the policy** page, make your selections, and then select **Next**.
1. On the **Test or turn on the policy** page, select either **Test it out first**, **Turn it on right away**, or **Keep it off**.
1. On the **Review your policy and create it** page, check that your settings are correct, and then select **Submit**.

## Learn more

- [Retention policies in Microsoft Teams](/microsoftteams/retention-policies).
- [Overview of data loss prevention](/microsoft-365/compliance/data-loss-prevention-policies)
