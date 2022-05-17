Windows Hello for Business provides organizations with a rich set of granular policy settings with which they can use to manage their devices and users. As noted before, you can manage and deploy Windows Hello for Business by using Group Policy or by using a modern management approach, with Microsoft Intune.

### Manage Windows Hello for Business with Intune

In Microsoft Intune, Windows Hello for Business can be deployed as a part of a device configuration profile. These profiles are used to configure various settings on Windows 10 and later devices. With device configuration profiles in Intune, you can enable or disable usage of Windows Hello for Business, and also configure the following settings:

 -  Minimum PIN length
 -  Maximum PIN length
 -  Lowercase letters in PIN
 -  Uppercase letters in PIN
 -  Special characters in PIN
 -  PIN expiration (days)
 -  Remember PIN history
 -  Enable PIN recovery
 -  Use a Trusted Platform Module (TPM)
 -  Allow biometric authentication
 -  Use enhanced anti-spoofing, when available
 -  Certificate for on-premises resources

You can also configure Windows Hello for Business settings in device enrollment policies on Intune. This enforces similar configuration settings as listed above, during device enrollment to Intune.

### Manage Windows Hello for Business with Group Policy

To manage Windows Hello for Business with Group Policy, you need a Windows 10 or later workstation to run the Group Policy Management Console, which provides the latest Windows Hello for Business and PIN Complexity Group Policy settings. You must configure the **Enable Windows Hello for Business** Group Policy setting for Windows to allow a user to attempt to enroll in Windows Hello for Business. A user can only attempt enrollment if this policy setting is set at **Enabled**.

You can configure the **Enable Windows Hello for Business** Group Policy setting for computers or users, depending of your deployment plans. For pilot deployments, we recommended selecting a group of users and deploying this Group Policy to the group. If both user and computer policy settings are deployed, the user policy setting has precedence.

To enable Windows Hello for Business by using Group Policy, you should create a new Group Policy object and then expand **Policies** under **User Configuration**, expand **Administrative Templates**, **Windows Component**, and select **Windows Hello for Business**.

When you open this setting, in the content pane, double-click **Use Windows Hello for Business** and then select **Enable** and select **OK**. You can also configure the option to use a certificate for on-premises authentication. There are also other Windows Hello for Business policy settings you can configure to manage your Windows Hello for Business deployment. These policy settings are computer-based policy settings; so they are applicable to any user that signs in from a computer with these policy settings. You can configure hardware security devices, biometrics settings and PIN complexity.

### Windows Hello for Business certificate

Windows Hello for Business provisioning performs the initial enrollment of the Windows Hello for Business authentication certificate. This certificate expires based on the duration configured in the Windows Hello for Business authentication certificate template. The Windows certificate auto-enrollment was updated to renew these certificates before they expire, which significantly reduces user authentication failures from expired user certificates.

The process requires no user interaction, provided the user signs in using Windows Hello for Business.
