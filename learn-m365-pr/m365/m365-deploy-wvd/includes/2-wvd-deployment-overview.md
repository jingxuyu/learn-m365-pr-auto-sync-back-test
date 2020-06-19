Before we walk through the deployment process, let's review some key terms and deployment options.

## Terminology

- *Workspace* - A workspace is a logical grouping of application groups in Windows Virtual Desktop. When a user signs in to Windows Virtual Desktop, they see a workspace with either a desktop or applications published to the application groups assigned to them.
- *Host pool* - A host pool is a collection of Azure virtual machines (VMs) that act as session hosts for Windows Virtual Desktop. 
  - *Pooled* - You can configure a *pooled* host pool where several users sign in and share a VM. Typically, none of those users would be a local administrator on the pooled VM. With pooled, you can use one of the recommended images that include Windows 10 Enterprise multi-session. This OS is exclusive to Windows Virtual Desktop.
  - *Personal* - A *personal* host pool is where each user has their own dedicated VM. Those users would typically be a local administrator for the VM. So they could install or uninstall apps without impacting other users.
- *Application groups* - An application group is a mechanism for grouping remote resources and assigning them to users.. An application group can be one of two types:

  - *RemoteApp*, where users access the applications you individually publish to the application group. You can create multiple RemoteApp app groups to accommodate different user scenarios. Use RemoteApp to virtualize an app that runs on a legacy OS or one that needs secured access to corporate resources.
  - *Remote Desktop*, where users access the full desktop. By default, the group **Desktop Application Group** is automatically created when you create a host pool.
  
- Load-balancing options -

   - *Breadth-first* - Default configuration for new non-persistent host pools. Distributes new user sessions across all available session hosts in the host pool. When you configure breadth-first load balancing, you may set a maximum session limit per session host in the host pool.
   - *Depth-first* - Distributes new user sessions to an available session host with the highest number of connections but has not reached its maximum session limit threshold. When you configure depth-first load balancing, you must set a maximum session limit per session host in the host pool.

## Configure virtual machines for host pool

When you create a Windows Virtual Desktop host pool, you can choose to create new VMs or register existing VMs to a host pool.

### Number of VMs

You can create up to 159 VMs when you first create your host pool. Each deployment creates four objects per VM, that can be seen in your resource group plus some additional Azure Resource Manager objects. So you can quickly reach the 800 Azure resources per deployment limit. You can add more VMs after you finish creating your host pool. Check the Azure VM and API limits for your resource group and subscription.

### VM sizing

For single-session scenarios, we recommend at least two physical CPU cores per VM. But check with your software vendor for sizing recommendations specific to your workload. VM sizing for single-session VMs likely align with physical device guidelines.

For multi-session VM sizing recommendations, see [Virtual machine sizing guidelines](https://docs.microsoft.com/windows-server/remote/remote-desktop-services/virtual-machine-recs?context=/azure/virtual-desktop/context/context#multi-session-recommendations).

### Image types

You choose the image type Azure uses to create the virtual machine, either Gallery or Storage blob.

- *Gallery* -  With this image type, you can select one of the recommended images from the drop-down menu like Windows 10 Enterprise multi-session + Office 365. If you don't see the image you want, select Browse all images and disks. Browse lets you select another image in your gallery or an image provided by Microsoft and other publishers.  

- *Storage blob* - Allows you to use your own image built through Hyper-V or on an Azure VM. You might use this option when you have an image you're using on-premises and just want to upload it and start using it in Azure immediately. When you select this option, there are some additional fields you need to complete.
  - *Image URI* - Enter the URL to the generalized VHD from your Azure Storage account.
  - *Use managed disks* - For Storage blob image type, we recommend you choose *Yes* for most VM configurations. You'd choose *No* where you want to use unmanaged disks for classic scenarios or to manage VHDs in your storage account.  
  - *Storage account* - You select the Azure storage account that contains your image.

## Select virtual network

We discussed the virtual network requirements in the module Prepare for Windows Virtual Desktop in Microsoft Azure. The virtual network you specify for the host pool provisioning process must be connected to your domain and allow outbound access to the URLs that support Windows Virtual Desktop. You'll need to join the virtual machines inside the virtual network to the domain.

If you're using Azure Active Directory Domain Services (Azure AD DS), we recommend that an Azure AD DS-managed domain is deployed into its own dedicated subnet. Don't deploy your VM in the same subnet as your Azure AD DS-managed domain. To
deploy your VM and connect to an appropriate virtual network subnet, we recommend one of the following options:

- Create or select an existing, subnet in the same the virtual network as your Azure AD DS-managed domain is deployed.
- Select a subnet in an Azure virtual network that is connected to it using Azure virtual network peering.

## Domain join VMs

To domain join the VMs you create, you need to specify the full Active Directory domain name to join like contoso.com. If you've set up a test environment with Azure AD DS, use the DNS domain name that's on the properties page for Azure AD DS like adds-contoso.onmicrosoft.com.

You'll need to specify an Administrator account so the provisioning process can join the VMs to the domain. This account must be assigned to the Active Directory Domain administrator role.

## Assign application groups

You can assign a user or group to both a remote desktop application group and a RemoteApp application group in the same host pool. However, users can only launch one type of application group per session. 

If a user or group is assigned to multiple RemoteApp application groups within the same host pool, they'll see all the applications published to those application groups.

## Connect to a workspace with a web or desktop client

You can access a Windows Virtual Desktop workspace from either a web browser or by using an app on your device. The browser option is helpful when you need to do some work and don't have your device with you. But for the best experience, we recommend you run the Windows Virtual Desktop client directly from your device. There are Windows Virtual Desktop clients that support the following types of devices:

- Windows
- Android
- macOS
- iOS
- Linux

To learn more about these clients and what operating system versions they support, see the links available at the end of this module.

## Bypass subscribe to workspace step

After you install the Windows Virtual Desktop client app and first launch it, you're prompted to subscribe to a workspace.

  :::image type="content" source="../media/5-subscribe-workspace.png" alt-text="Screenshot of the subscribe to workspace form with the URL pasted in.":::

To bypass that step and simplify the process for your users, set up email discovery with your domain registrar. Add a DNS TXT record that has the following properties for the domain associated with your email:


|Property  |Value  |
|---------|---------|
|Host     | _msradc      |
|Text     | `https://rdweb.wvd.microsoft.com/arm/api/feeddiscovery/webfeeddiscovery.aspx`    |
|TTL     | 300    |


In the following units, you'll learn how to connect to a workspace by using both a web and desktop client.
