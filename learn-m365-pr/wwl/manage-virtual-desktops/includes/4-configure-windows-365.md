Setting up Windows 365 is primarily done in the Endpoint Manager admin center. The following is a general summary of the basic steps needed to set up your system to provision on-demand Cloud PCs to your users.

### Assign licenses to users

Before a user can use a Cloud PC, you must assign a Windows 365 license to that user. You can assign the licenses to users or groups using one of the administrative portals or PowerShell. To assign licenses using the Azure AD admin center, perform the following.

1.  Sign in to the Azure AD admin center with a license administrator account.
2.  Select **Licenses** to open a page where you can see and manage all licensable products in the organization.
3.  Select a user or group, and then use the **Select** button at the bottom of the page to confirm your selection.
4.  Under All products, select **Windows 365.** Select **Assign** at the top of the page.
5.  On the Assign license page, select **Users and groups** to open a list of users and groups.
6.  Select **Assign** at the bottom of the page.

### Create an Azure network connection

An Azure network connection (ANC) is required so that Cloud PCs can join the organization's domain and access on-premises resources. You'll be connecting to a virtual network configured in Azure that has been set up for connectivity with the on-premises domain controller and network. Work with your organization's Azure administrator to identify this.

To create an Azure network connection:

1.  Sign in to the **Microsoft Endpoint Manager admin center** with an account that is an Intune Administrator in Azure AD and has owner permissions to the virtual network in the Azure subscription.
2.  Select **Devices** > **Windows 365** (under **Provisioning**) > **Azure network connection** > **Create connection**.
3.  On the **Network details** page, enter a **Name** for the new connection. The connection name must be unique within the customer tenant.
    
    :::image type="content" source="../media/connection-name-c4ff26d6.png" alt-text="Screenshot of connection name":::
    
4.  Select a **Subscription** and **Resource group** for the new connection. Create a new resource group or select an existing one that contains your Cloud PC resources.
5.  Select a **Virtual network** and **Subnet** and select **Next**.
6.  On the **AD domain** page, provide the **AD domain name**, **Organizational unit** (optional) and an **AD domain username and password** for the service account used for connecting the Cloud PCs to your Active Directory domain.
7.  Select **Next**.
8.  On the **Review + Create** page, select **Create**.

### Learn More
-  [Create Azure network connection](/windows-365/enterprise/create-azure-network-connection?azure-portal=true)
-  [Edit Azure network connection](/windows-365/enterprise/edit-azure-network-connection?azure-portal=true)
-  [Delete Azure network connection](/windows-365/enterprise/delete-azure-network-connection?azure-portal=true)
### Configure a custom device image (optional)

Windows 365 provides a built-in gallery of Windows Enterprise images accessible through the provisioning policy creation flow. These images are updated monthly with the latest security updates so that end users have a secure and seamless experience.

 -  Images with pre-installed Microsoft 365 Apps: Microsoft 365 Apps and Teams optimizations are already installed.
 -  Images with OS optimizations: These are Windows Enterprise images optimized for improved performance on virtualized environments and on lower end hardware configurations.

As most device configurations are applied through configuration policies, these base images should be sufficient for many organizations. However, if a custom image is needed, you can create and upload up to 20 custom generalized images. The custom image must be added to your Azure subscription before it can be used with Windows 365. Once that's done, sign in to the Microsoft Endpoint Manager admin center, select **Devices** > **Windows 365** > **Device images** > **Add**. Select an image from the available list, and select **Add**.
### Learn More
-  [Add or delete custom device images](/windows-365/enterprise/add-device-images?azure-portal=true)

### Create provisioning policies

Cloud PCs are created and assigned to users based on provisioning policies. After provisioning policies are created and assigned to the Azure AD user security groups or Microsoft 365 Groups, the Windows 365 service checks for appropriate licensing for each user and configures the Cloud PCs accordingly.

Creating a provisioning policy requires the following steps:

1.  Sign in to the Microsoft Endpoint Manager admin center, select **Devices** > **Windows 365** > **Provisioning policies** > **Create policy**.
    
    :::image type="content" source="../media/create-policy-bd0ad87a.png" alt-text="Screenshot of create policy,":::
    
2.  On the **General** page, enter a **Name** for the new policy.
3.  For **On-premises network connection**, select the connection to use for this policy > **Next**.
4.  On the **Image** page, for **Image type**, select one of the following options:
    
     -  **Gallery image**: Choose **Select** > select an image from the gallery > **Select**.
     -  **Custom image**: Choose **Select** > select an image from the list > **Select**.
5.  Select **Next**.
6.  On the **Assignments** page, choose **Select groups** > choose the groups you want this policy assigned to, choose **Select** and then **Next**.
7.  On the **Review + create** page, select **Create**.

### Learn More
-   [Create provisioning policies](/windows-365/enterprise/create-provisioning-policy?azure-portal=true)

> [!NOTE]
> It can take up to 60 minutes for the policy creation process to complete, depending on when the Azure AD connect sync last happened.

### Configure and apply device and app configuration profiles

Once the initial setup is complete, Cloud PCs are configured just like a physical device. You create configuration profiles (or leverage existing ones if applicable) and assign apps to users, devices, and groups just like any other device.
