Intune Mobile Application Management (MAM) refers to the suite of Intune management features you can use to publish, push, configure, secure, monitor, and update mobile apps for your users on mobile devices such as Windows, Android and iOS platforms. MAM protects an organization's data within an application by using Microsoft Intune app protection policies that help protect your company data and prevent data loss.

If you use MAM without enrollment (MAM-WE), a work or school-related app that contains sensitive data can still be managed on almost any device, including personal devices in bring-your-own-device (BYOD) scenarios. Many productivity apps, such as the Microsoft Office apps, can be managed by Intune MAM.

Your employees use mobile devices for both personal and work tasks. While making sure your employees can be productive, you want to prevent data loss, intentional and unintentional. You will also want to protect company data that is accessed from devices that are not managed by you. You can use Intune app protection policies independent of any mobile-device management (MDM) solution. This independence helps you protect your company’s data with or without enrolling devices in a device management solution. By implementing app-level policies, you can restrict access to company resources and keep data within the purview of your IT department.

Intune MAM supports two configurations:

- **Intune MDM + MAM:** IT administrators can only manage apps using MAM and app protection policies on devices that are enrolled with Intune MDM. To manage apps using MDM + MAM, you should use the Intune console in the Azure portal at [https://portal.azure.com](https://portal.azure.com/)

- **MAM without device enrollment:** MAM without device enrollment (MAM-WE) allows IT administrators to manage apps using MAM and app protection policies on devices not enrolled with Intune MDM. This means apps can be managed by Intune on devices enrolled with third-party Enterprise Mobility Management (EMM) providers. To manage apps using MAM-WE, you should use the Intune console in the Azure portal at [https://portal.azure.com](https://portal.azure.com/) . Also, apps can be managed by Intune on devices enrolled with third-party EMM providers or not enrolled with an MDM at all.

The MAM-WE configuration is for organizations that have decided to allow devices, not managed by Intune, to access organization data but still want to manage data on those devices through MAM app protection policies. The Intune MDM + MAM configuration is for organizations using Intune for device management and MAM for application management.

