Of course, all organizations use information slightly differently. However, the general pathway by which files are created, managed, updated, and destroyed is often broadly similar. In your legal company, you're concerned that your compliance with regulations might not be as good as it should be. You're investigating file lifecycles to analyze this problem further.

Here, you'll learn about the typical lifecycle of the files in your organization.

## Lifecycle summary

Not all data is created equal. Some data is more sensitive and requires a stronger level of protection and control than other types. The kinds of information that need protecting depends on your internal security requirements and compliance obligations. Because every organization may have different governance or compliance standards, it's important to allow customization of classification policies.

For instance, a beverage company needs to protect the secret recipe to its most famous soft drink. However, a finance company's cafeteria recipes are not so critical to everyday business. There are general guidelines for more obvious sensitive data, such as credit card and social security numbers, but no two organizations classify data the same way.

Let's look at the journey of a file through your company and discuss how Microsoft technologies can help protect the data within that file.

> [!div class="centered"]
> :::image type="complex" source="../media/story-of-file.png" alt-text="Infographic showing how Microsoft technologies protect a file from creation through editing and cloud storage." lightbox="../media/story-of-file.png" border="false":::
>	First the file is created, then the user opens the file for editing, the user collaborates on the file with others through SharePoint Online, which may lead to a user opening the file on mobile, and finally the file is uploaded to other cloud services for sharing externally.
> :::image-end:::

Now, let's examine these lifecycle stages in more detail.

1. **File is created**

    Your legal department creates a slide deck to share with clients in PowerPoint. It's a generic deck that should be tailored for each client. The file isn't _immediately_ given any sensitivity labeling. Sensitivity labels enforce information protection based on labels added to any documents created in an Office app, so sensitivity labels will be added to each customized deck based on different client needs.

1. **User edits the file**

    A paralegal changes the presentation to include client specific information around the company's financial information. The paralegal adds a **Confidential** sensitivity label. This ensures the file has the right protection.

1. **User shares the file with another user in the organization**

    The paralegal is working closely with an attorney on a related case and shares the presentation from a folder in SharePoint. As an additional layer of protection, Data Loss Prevention (DLP) policies help prevent the accidental or inadvertent sharing of sensitive documents and emails.

1. **User opens the file on their phone**

    The attorney opens the file on their phone, Intune enforces protection of the data.

1. **User uploads the file to another cloud service such as Dropbox**

    If a user uploads the data to other clouds for external sharing, services such as Microsoft Defender for Cloud Apps can apply policies based on the data's labels.
