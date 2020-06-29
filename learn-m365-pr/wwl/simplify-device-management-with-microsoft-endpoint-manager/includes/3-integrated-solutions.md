## Endpoint Manager

Microsoft Endpoint Manager helps deliver the modern workplace and modern
management to keep your data secure, in the cloud and on-premises.
Endpoint Manager includes the services and tools you use to manage and
monitor mobile devices, desktop computers, virtual machines, embedded
devices, and servers.

Endpoint Manager includes the following services:

- **Microsoft Intune**: Intune is a 100% cloud-based mobile device
management (MDM) and mobile application management (MAM) provider
for your apps and devices. It lets you control features and
settings on Android, Android Enterprise, iOS/iPadOS, macOS, and
 Windows 10 devices. It integrates with other services, including
Azure Active Directory (AD), mobile threat defenders, ADMX
templates, Win32 and custom LOB apps, and more.

  If you have on-premises infrastructure, such as Exchange or an Active Directory, the Intune connectors are also available:

  - The **Intune Connector for Active Directory** adds entries to your
  on-premises Active Directory domain for computers that enroll
  using Windows Autopilot.

  - The **Intune Exchange connector** allows (or blocks) device access
  to your Exchange servers if devices are enrolled in Intune, and
  compliant with your policies.

  - The **Intune certificate connector** processes certificate requests
  from devices that use certificates for authentication and S/MIME
  email encryption.

As part of Endpoint Manager, use Intune to create and check for compliance, and deploy apps, features, and settings to your devices using the cloud.

- **Configuration Manager**: Configuration Manager is an on-premises
management solution to manage desktops, servers, and laptops that
are on your network or internet-based. You can cloud-enable it to
integrate with Intune, Azure Active Directory (AD), Microsoft
Defender ATP, and other cloud services. Use Configuration Manager
to deploy apps, software updates, and operating systems. You can
also monitor compliance, query and act on clients in real time,
and much more.

  As part of Endpoint Manager, continue to use Configuration Manager as
you always have. If you're ready to move some tasks to the cloud,
consider co-management.

- **Co-management**: Co-management combines your existing on-premises
Configuration Manager investment with the cloud using Intune and other
Microsoft 365 cloud services. You choose whether Configuration Manager
or Intune is the management authority for the seven different workload
groups.

- **Desktop Analytics**: Desktop Analytics is a cloud-based service
that integrates with Configuration Manager. It provides insight
and intelligence for you to make more informed decisions about the
update readiness of your Windows clients. The service combines
data from your organization with data aggregated from millions of
devices connected to the Microsoft cloud. It provides information
on security updates, apps, and devices in your organization, and
identifies compatibility issues with apps and drivers. Create a
pilot for devices most likely to provide the best insights for
assets across your organization.

- **Windows Autopilot**: Windows Autopilot sets up and pre-configures
new devices, getting them ready for use. It's designed to
simplify the lifecycle of Windows devices, for both IT and end
users, from initial deployment through end of life.

  As part of Endpoint Manager, use Autopilot to preconfigure devices,
and automatically enroll devices in Intune. You can also integrate
Autopilot with Configuration Manager and co-management for more
complex device configurations (in preview).

- **Azure Active Directory (AD)**: Azure AD is used by Endpoint
Manager for identity of devices, users, groups, and multi-factor
authentication (MFA). **Azure AD Premium**, which may be an
additional cost, has additional features to help protect devices,
apps, and data, including dynamic groups, auto-enrollment, and
conditional access.

- **Endpoint Manager admin center**: The admin center is a one-stop
web site to create policies and manage your devices. It plugs-in
other key device management services, including groups, security,
conditional access, and reporting. This admin center also shows
devices managed by Configuration Manager and Intune (in preview).

:::image type="content" source="../media/3-endpoint-manager-admin-center.png" alt-text="Endpoint Manager Admin Console":::

### Choose what's right for you

There are a few ways to determine what's right for your organization.
Your next steps depend on what your organization does. Consider what
you're trying to achieve.

For example:

- If you constantly provision new devices, then start with Windows
Autopilot.

- If you add rules and control settings for your users, apps, and
devices, then start with Intune.

- If you currently use Configuration Manager to deploy apps, and want
to use conditional access based on security requirements, then
start with co-management.

- If you currently use Configuration Manager and are responsible for
keeping Windows 10 devices up-to-date, then start with Desktop
Analytics.

- If you're getting started with MDM and MAM, or use ADMX templates
to control Office, Microsoft Edge, and Windows settings, then
start with Intune.

You can also think of Endpoint Manager in three parts: cloud,
on-premises, and cloud + on-premises:

- **Cloud**: All data is stored in Azure. And, no more data centers.
This approach gives you the mobility benefits of the cloud, and
the security benefits of Azure.

- **On-premises**: If you have an on-premises infrastructure that
includes Configuration Manager, or aren't ready to use the cloud,
then you can keep your existing systems.

- **Cloud + on-premises**: Many environments are mixed, and use a
cloud-attach approach. Meaning they use a combination of cloud and
on-premises. For new devices, use the benefits of Intune to access
and protect data. If you use Configuration Manager, connect to the
cloud for additional functionality and analytics. If you want to
move some workloads to the cloud, then co-management is a good
option.
