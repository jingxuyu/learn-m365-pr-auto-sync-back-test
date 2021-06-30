Azure Virtual Desktop on Microsoft Azure is a desktop and app virtualization service that runs on the cloud. Azure Virtual Desktop works across devices, like Windows, Mac, iOS, Android, and Linux, with apps that you can use to access remote desktops and apps. You can also use most modern browsers to access Azure Virtual Desktop-hosted experiences.

## Provide the best user experience

Users have the freedom to connect to  Azure Virtual Desktop with any device over the internet. They use an Azure Virtual Desktop client to connect to their published Windows desktop and applications. This client could either be a native application on the device or the Azure Virtual Desktop HTML5 web client.

You can make sure your session host virtual machines (VMs) run near apps and services that connect to your datacenter or the cloud. So users stay productive and don't encounter long load times.

User sign-in to Azure Virtual Desktop is extremely fast because user profiles are containerized by using FSLogix. At sign-in, the user profile container is dynamically attached to the computing environment. The user profile is immediately available and appears in the system exactly like a native user profile.

You can provide individual ownership through personal (persistent) desktops. For example, you may want to provide personal remote desktops for members of an engineering team. They'd be able to add or remove programs without impacting other users on that remote desktop.

## Enhance security

Azure Virtual Desktop provides centralized security management for user's desktops with Azure Active Directory (Azure AD). You can enable multi-factor authentication to secure user sign-ins. You can also secure access to data by assigning granular role-based access controls to users.

With Azure Virtual Desktop, the data and apps are separated from the local hardware and runs them instead on a remote server. So the risk of confidential data being left on a personal device is reduced.

User sessions are isolated in both single and multi-session environments.

Azure Virtual Desktop also improves security by using reverse connect technology which is a more secure connection type than the Remote Desktop Protocol. We don't open inbound ports to the session host VMs.

## Simplify management

Azure Virtual Desktop is an Azure service which will be familiar to Azure administrators. You use Azure Active Directory and role-based access controls to manage access to resources. Also with Azure, you get  tools to automate VM deployments, manage VM updates, and provide disaster recovery. As with other Azure services, Azure Virtual Desktop uses Azure Monitor for monitoring and alerts. This lets admins identify issues through a single interface.

## Manage performance

Azure Virtual Desktop gives you options to load balance users on your VM host pools. **Host pools** are collections of VMs with the same configuration assigned to multiple users. For the best performance, you can configure load balancing to occur as users sign in (breadth mode). With breadth mode, users are sequentially allocated across the host pool for your workload. To save costs, you can configure your VMs for depth mode load balancing where users are fully allocated on one VM before moving to the next. Azure Virtual Desktop provides tools to automatically provision additional VMs when incoming demand exceeds a specified threshold.

## Deploy multi-session Windows 10

Azure Virtual Desktop lets you use Windows 10 Enterprise multi-session, the only Windows client-based operating system that enables multiple concurrent users on a single virtual machine (VM). Azure Virtual Desktop also provides a more consistent experience with broader application support compared to Windows Server-based operating systems.

## Bring your licenses

Azure Virtual Desktop is available to you at no additional cost if you have an eligible Microsoft 365
license. Just pay for the Azure resources used by Azure Virtual Desktop.

- Bring your eligible Windows or Microsoft 365 license to get Windows 10 Enterprise and Windows 7 Enterprise desktops and apps at no additional cost.
- If you're an eligible Microsoft Remote Desktop Services (RDS) Client Access License (CAL) customer, Windows Server Remote Desktop Services desktops and apps are available at no additional cost.

## Save on compute costs

Buy one-year or three-year Azure Reserved Virtual Machine Instances to save you up to 72 percent versus pay-as-you-go pricing. You can pay for a reservation up front or monthly. Reservations provide a billing discount and don't affect the runtime state of your resources.
