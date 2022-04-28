Azure AD pass-through authentication (PTA) was introduced in earlier training that examined user authentication options. This unit examines in greater detail the mechanics of how PTA works and how it's enabled.

So why should organizations implement PTA?

Well, users typically prefer to maintain one set of sign-in credentials for both cloud and on-premises resources. The common sentiment is the fewer usernames and passwords to remember, the better.

Many organizations achieve this goal by using Azure AD Connect with password hash synchronization. With this feature, password validation is completed in the cloud.

However, some organizations prefer to have all authentication done on-premises. Companies that prefer on-premises authentication usually have a security requirement to immediately enforce on-premises user account states, password policies, and sign-in hours. In the past, organizations who preferred on-premises authentication would deploy Active Directory Federation Services (AD FS) and configure their Azure AD tenant in federated mode. Each authentication request for resources on-premises or in the cloud was then directed to the AD FS server that was deployed locally.

The problem with this AD FS solution is that deployment and management of the locally deployed AD FS infrastructure was often too demanding, costly, and complex for many organizations. To address this issue, Microsoft updated Azure AD Connect to include an optional feature called Azure AD pass-through authentication.

Azure AD pass-through authentication helps ensure that password validation for services that rely on Azure AD is always run against an on-premises Active Directory. If PTA fails, automatic failover to password hash synchronization is run if it’s enabled. Unlike the AD FS solution, PTA is easy to implement and maintain.

### The Azure AD pass-through authentication process

Azure AD pass-through authentication is configured by using Azure AD Connect. It works by using an on-premises agent that listens for external password validation requests. This agent can be deployed to one or more servers to provide high availability. There's no need to deploy this server to the perimeter network, as all communication is outbound only. A server that runs the agent for pass-through authentication should be joined to the Active Directory domain where users are located.

The following graphic shows how the user sign-in process works when implementing PTA. In summary:

 -  A user is presented with an Azure AD sign-in page when they access a cloud service that relies on Azure AD.
 -  After the user enters their credentials, the Azure AD service checks if the connector for pass-through authentication is configured for the user’s domain.
 -  If it is, credentials are placed on the connector queue for validation.
 -  A connector agent deployed on-premises then retrieves the user's credentials and authenticates them against the locally deployed Active Directory.
 -  The Active Directory's response is returned to the connector, which in turn provides this response to Azure AD.

:::image type="content" source="../media/data-flow-using-pta-786afe2d.jpg" alt-text="graphic showing data flow with passthrough authentication":::


### Enabling Azure AD pass-through authentication

To enable Azure AD pass-through authentication, an organization must:

 -  Run the **Azure AD Connect Setup Wizard.**
 -  Select the **Pass-through authentication** option on the **User Sign-in** page.

The first connector for pass-through authentication is deployed on the same server where Azure AD Connect runs. It's recommended that organizations deploy an extra connector on at least one more server. Doing so will help achieve load balancing between the set of available connectors for both high availability and redundancy. The Azure AD Application Proxy Connector can be downloaded as a separate installation for other servers.

All ports required by Azure AD pass-through authentication must be available. These ports are listed in the following table.

:::row:::
  :::column:::
    **Port**
  :::column-end:::
  :::column:::
    **Description**
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    80
  :::column-end:::
  :::column:::
    Enables outbound HTTP traffic for security validation such as TLS/SSL certificate revocation lists.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    443
  :::column-end:::
  :::column:::
    Enables user authentication against Azure AD.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    8080/443
  :::column-end:::
  :::column:::
    Enables the Connector bootstrap sequence and Connector automatic update.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    9090
  :::column-end:::
  :::column:::
    Enables Connector registration (required only for the Connector registration process).
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    9091
  :::column-end:::
  :::column:::
    Enables Connector trust certificate automatic renewal.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    9352, 5671
  :::column-end:::
  :::column:::
    Enables communication between the Connector and the Azure AD service for incoming requests.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    9350
  :::column-end:::
  :::column:::
    \[Optional\] Enables better performance for incoming requests.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    10100–10120
  :::column-end:::
  :::column:::
    Enables responses from the connector back to Azure AD.
  :::column-end:::
:::row-end:::


**Additional reading.** For more information, see [User sign-in with Azure AD Pass-through Authentication](https://aka.ms/lusqtt?azure-portal=true).
