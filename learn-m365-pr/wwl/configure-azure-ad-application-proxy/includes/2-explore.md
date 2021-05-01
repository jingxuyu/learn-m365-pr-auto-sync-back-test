Azure Active Directory (AD) Application Proxy helps you support remote workers by publishing on-premises applications to be accessed over the internet. You can publish these applications through the Azure portal to provide secure remote access from outside your network.

Employees today want to be productive at any place, at any time, and from any device. They want to work on their own devices, whether they're tablets, phones, or laptops. They also require access to all their applications, both SaaS apps in the cloud and corporate apps on-premises. Providing access to on-premises applications has traditionally involved virtual private networks (VPNs) or perimeter networks.

A modern workforce in the mobile-first, cloud-first world needs a modern remote access solution. Azure AD Application Proxy is a feature of Azure Active Directory that offers remote access as a service, which means that it's easy to deploy, use, and manage.

This unit examines the benefits of Azure AD Application Proxy, the type of applications that work with it, and how it works.

### Benefits of Azure AD Application Proxy

Azure AD Application Proxy provides a simple, secure, and cost-effective remote access solution to all your on-premises applications. Azure AD Application Proxy is:

 *  Simple
    
     *  You don't need to change or update your applications to work with Application Proxy.
     *  Your users get a consistent authentication experience. They can use the **My Apps** portal to get single sign-on to both SaaS apps in the cloud and your apps on-premises.
 *  Secure
    
     *  When you publish your apps using Azure AD Application Proxy, you can take advantage of the rich authorization controls and security analytics in Azure. You get cloud-scale security and Azure security features like conditional access and two-step verification.
     *  You don't have to open any inbound connections through your firewall to give your users remote access.
 *  Cost-effective
    
     *  Application Proxy works in the cloud, so you can save time and money. On-premises solutions typically require you to set up and maintain perimeter networks, edge servers, or other complex infrastructures.

Azure AD Application Proxy provides single sign-on (SSO) to applications that use Integrated Windows Authentication (IWA), or claims-aware applications. If your application uses IWA, Application Proxy impersonates the user using Kerberos Constrained Delegation to provide SSO. If you have a claims-aware application that trusts Azure Active Directory, SSO works because the user was already authenticated by Azure AD.

### What type of applications work with Azure AD Application Proxy?

With Azure AD Application Proxy, you can access different types of internal applications:

 *  Web applications that use [Integrated Windows Authentication](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-single-sign-on-with-kcd?azure-portal=true) for authentication
 *  Web applications that use form-based or [header-based](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-single-sign-on-with-ping-access?azure-portal=true) authentication
 *  Web APIs that you want to expose to rich applications on different devices
 *  Applications hosted behind a [Remote Desktop Gateway](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-integrate-with-remote-desktop-services?azure-portal=true)
 *  Rich client apps that are integrated with the Active Directory Authentication Library (ADAL)

Once your app is published with Application Proxy, it can be managed it like any other enterprise app in the Azure portal. You can:

 *  use Azure Active Directory security features like conditional access and two-step verification.
 *  control user permissions.
 *  customize the branding for your app.

### How does Azure AD Application Proxy work?

There are two components that must be configured to make Azure AD Application Proxy work:

 *  **A connector.** The connector is a lightweight agent that sits on a Windows Server inside your network. The connector controls the traffic flow from the Application Proxy service in the cloud to your application on-premises. It only uses outbound connections, so you don't have to open any inbound ports or put anything in the perimeter network. The connectors are stateless and pull information from the cloud, as necessary. For more information about connectors, like how they load-balance and authenticate, see [Understand Azure AD Application Proxy connectors](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors?azure-portal=true).
 *  **An external endpoint.** The external endpoint is how your users reach your applications while outside of your network. They can either go directly to an external URL that you determine, or they can access the application through the MyApps portal. When users go to one of these endpoints, they authenticate in Azure AD and then are routed through the connector to the on-premises application.

The following steps, which are illustrated in the diagram below, describe how the application proxy works:

1.  The user accesses the application through the Application Proxy service and is directed to the Azure AD sign-in page to authenticate.
2.  After a successful sign-in, a token is generated and sent to the client device.
3.  The client sends the token to the Application Proxy service, which retrieves the user principal name (UPN) and security principal name (SPN) from the token, then directs the request to the Application Proxy connector.
4.  If you've configured single sign-on, the connector performs any other authentication required for the user.
5.  The connector sends the request to the on-premises application.
6.  The response is sent through the Application Proxy service and connector to the user.

:::image type="content" source="../media/steps-showing-how-app-proxy-works-0cc8e8d6.jpg" alt-text="graphic showing the steps that describe how the application proxy works":::


## Knowledge check

Choose the best response for the following question. Then select “Check your answers.”