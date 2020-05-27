A virtual directory is used to allow access to a web application such as Exchange ActiveSync, Outlook on the web, or the Autodiscover service. 

You can configure virtual directories using the EAC or the Exchange Management Shell. If you use the Shell to view the properties of an Outlook on the web virtual directory, be aware that the information returned is a subset of the information that's available. 

To view or configure Outlook on the web virtual directory properties with the EAC, in the EAC click **Servers**, and then click **Virtual Directories**. Some settings, such as the **Internal URL** for the website, can be configured, but some settings, such as Outlook Web App version, are read-only and are for information only. 

If an Outlook on the web virtual directory isn't working the way you expect, you can reset it. This deletes the virtual directory and recreates it using the default settings. Although any customized settings are lost, you're forced to select a location for a text document to back up the current settings. 

To reset the virtual directory, in the EAC, click **Servers > Virtual directories**. Select the virtual directory you want to view or configure, and then click **Reset**. 

To view or configure Outlook on the web virtual directory properties with PowerShell use the **Get-OWAVirtualDirectory** and **Set-OwaVirtualDirectory** cmdlets. 

## Learn more 
 
- [View or configure Outlook on the web virtual directories in Exchange Server](https://docs.microsoft.com/exchange/clients/outlook-on-the-web/virtual-directories?view=exchserver-2019&azure-portal=true) 
- [PowerShell Reference Library](https://docs.microsoft.com/powershell/windows/get-started?view=win10-ps&azure-portal=true) 

