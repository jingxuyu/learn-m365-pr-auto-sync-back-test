When troubleshooting Windows Autopilot, the key things to verify are:

 -  **Configuration**. Has Azure AD and Microsoft Intune (or an equivalent MDM service) been configured as specified in Windows Autopilot configuration requirements?
 -  **Network connectivity**. Can the device access the services described in Windows Autopilot networking requirements?
 -  **Autopilot OOBE behavior**. Were only the expected out-of-box experience screens displayed? Was the Azure AD credentials page customized with organization-specific details as expected?
 -  **Azure AD join issues**. Was the device able to join Azure AD?
 -  **MDM enrollment issues**. Was the device able to enroll in Microsoft Intune (or an equivalent MDM service)?

### Troubleshoot Autopilot OOBE issues

If the expected Autopilot behavior does not occur during the out-of-box experience (OOBE), it's useful to see whether the device received an Autopilot profile and what settings that profile contained. Depending on the Windows release, there are different mechanisms available to do that.

You can use the Event Tracing for Windows (ETW) can be used to capture detailed information from Autopilot and related components. The resulting ETW trace files can then be viewed using the Windows Performance Analyzer or similar tools.<br>

Information about the Autopilot profile settings are stored in the registry on the device after they are received from the Autopilot deployment service. These can be found at HKLM\\SOFTWARE\\Microsoft\\Provisioning\\Diagnostics\\Autopilot.<br>

To see details related to the Autopilot profile settings and OOBE flow, Windows adds event log entries. These can be viewed using Event Viewer, navigating to the log at Application and Services Logs –&gt; Microsoft –&gt; Windows –&gt; Provisioning-Diagnostics-Provider –&gt; Autopilot. The following events may be recorded, depending on the scenario and profile configuration.<br>

:::row:::
  :::column:::
    **Event ID**
  :::column-end:::
  :::column:::
    **Type**
  :::column-end:::
  :::column:::
    **Description**
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    100
  :::column-end:::
  :::column:::
    Warning
  :::column-end:::
  :::column:::
    "Autopilot policy \[name\] not found." This event is typically a temporary problem, while the device is waiting for an Autopilot profile to be downloaded.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    171
  :::column-end:::
  :::column:::
    Error
  :::column-end:::
  :::column:::
    "AutopilotManager failed to set TPM identity confirmed. HRESULT=\[error code\]." This event indicates an issue performing TPM attestation, needed to complete the self-deploying mode process.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    172
  :::column-end:::
  :::column:::
    Error
  :::column-end:::
  :::column:::
    "AutopilotManager failed to set Autopilot profile as available. HRESULT=\[error code\]." This event is typically related to event ID 171.
  :::column-end:::
:::row-end:::


### Windows AutoPilot Diagnostics

Windows AutoPilot can now aggregate a lot of the troubleshooting techniques seen above into a more easily readable format to isolate issues that occur. This can be executed from a PowerShell command directly on the device.

Open PowerShell command and enter the following (Accept download prompts):

```powershell
Set-ExecutionPolicy ByPass
Install-Script Get-AutoPilotDiagnostics -force
Get-AutoPilotDiagnostics -Online
```

Once connected to the tenant with an account that has appropriate credentials, through the GraphAPI extensions for Intune, a list of policies, apps, and status will be displayed.

### Troubleshoot Azure AD join issues

The most common issue joining a device to Azure AD is related to Azure AD permissions. Ensure the correct configuration is in place to allow users to join devices to Azure AD. Errors can also happen if the user has exceeded the number of devices that they are allowed to join, as configured in Azure AD.

Error code 801C0003 will typically be reported on an error page titled "Something went wrong." This error means that the Azure AD join failed.

### Troubleshoot Intune enrollment issues

See this knowledge base article for assistance with Intune enrollment issues. Common issues include incorrect or missing licenses assigned to the user or too many devices enrolled for the user.

Error code 80180018 will typically be reported on an error page titled "Something went wrong." This error means that the MDM enrollment failed.

### Troubleshoot Device Import

When importing a device CSV file, if nothing happens and a *'400' error appears in network trace with error body "Cannot convert the literal '\[DEVICEHASH\]' to the expected type 'Edm.Binary* error appears, the device hash within the file is either corrupted or the hash may not be properly padded in the file. This may require a minor edit to the file.

For more information, see [Troubleshooting Windows Autopilot (level100/200)](https://aka.ms/AA6d57a) and [Troubleshooting Windows Autopilot](https://aka.ms/AA80h34).
