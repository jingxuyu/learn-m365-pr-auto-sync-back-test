It’s important that you know what’s happening in your organization’s cloud app environment. If Contoso's users are using apps that you don’t know about, they might be introducing malware without your knowledge. Contoso might suffer from data loss when users share content without proper controls. However, you must allow users to use the apps they need, and from devices that they might own. In short, you must strike a balance between users’ needs, and the security of Contoso and its data. 

Some of these apps might use Azure Active Directory (Azure AD) as the identity provider. Other apps might not, and might instead rely on an alternative identity provider. But by using Microsoft Cloud App Security, you can implement access and session controls with any supported identity provider. 

> [!NOTE]
> If your users' apps rely on Azure AD, access and session controls are already fully integrated into Azure AD’s Conditional Access tool.

## What is Conditional App Access Control?

You can use Conditional App Access Control in Cloud App Security to monitor and control user app access and sessions based on configurable policies. The following table describes how you can use these policies. 

| Action                                | Description                                                  |
| ------------------------------------- | ------------------------------------------------------------ |
| Prevent data  exfiltration            | Block  download, and prevent cut, copy, and paste of sensitive documents |
| Protect on  download                  | Require protection  of sensitive documents with Azure Information Protection before users can  download them |
| Prevent  upload of unlabeled files    | Prevent the  upload of sensitive content until it has been correctly labelled by the user. |
| Block  potential malware              | Block files  identified as potentially malicious from being uploaded by your users |
| Monitor user  sessions for compliance | Monitor risky  user sessions by logging user activities      |
| Block access                          | Block  specific users or specific apps based on risk factors |
| Block custom  activities              | Scan content  for sensitive information, and block where required |

 

## How it works

You start by creating a session policy in Cloud App Security. This session policy enables you to control user sessions. In effect, the user session is redirected through a reverse proxy instead of connecting directly to the targeted app. This means that all user access is directed through Cloud App Security, providing you with the controls discussed earlier. 

When you protect a session with a proxy, all the app’s URLs and cookies are modified with a Cloud App Security suffix. For example, if the app URL is `app.Contoso.com`, the modified URL is `app.Contoso.com.mcas.ms`.

> [!TIP]
> Using this method avoids you having to install anything on a device in order to redirect app access through the proxy.

## Managed device identification

The decision that you make about allowing or blocking access and files might be impacted if you know more about the device. For example, you might be more flexible with sensitive content actions if the device being used to access the content is a managed device. 

To help you with this determination, Cloud App Security can verify whether the device: 

- Is Microsoft Intune compliant
- Is a Hybrid Azure AD joined device
- Has client certificates in a trusted chain

Azure AD Conditional Access policies enable device information for Intune Compliant and Hybrid joined devices to be submitted to Cloud App Security. You can then use an access or session policy that implements device state as a filter. 

Certificates work in a different way. When a client certificate is used, Cloud App Security verifies that the certificate is valid, unrevoked, and is under the correct root or intermediate Certificate Authority (CA). You can create and use a policy to determine device management based on client certificates by selecting **Settings** in the Cloud App Security portal. Then select the **Device identification** tab. You can then upload as many root or intermediate CA certificates as you require. 

> [!IMPORTANT]
> You must upload certificates in the PEM format. 

:::image type="content" source="../media/device-identification.png" alt-text="A screenshot that displays the Device identification page in the Cloud App Security portal.":::


## Onboard and deploy Conditional Access App Control for any app

You can use session controls in Cloud App Security to work with any app. This might include non-featured SaaS apps, line-of-business apps, or even on-premises apps hosted by Azure AD Application Proxy. However, your environment must meet certain prerequisites discussed below. You must have:

- An Azure AD Premium P1 or P2 license, or a license required by another identity provider
- A Microsoft Cloud App Security license
- Apps that are configured for single sign-on (SSO)
- Apps that support one of the following authentication protocols:
   - SAML 2.0
   - OpenID Connect

### To deploy any app

To deploy any app so that it is controlled by Cloud App Security Conditional Access App Control, use the following high-level procedure:

1. Configure your identity provider to work with Cloud App Security
2. Configure the users that deploy the app
3. Configure the app that you are deploying
4. Verify that the app is working correctly
5. Enable the app for use in your organization
6. Update the Azure AD policy

> [!NOTE]
> You can review more detail in the following document: [To deploy any app](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-any-app#to-deploy-any-app?aure-portal=true).