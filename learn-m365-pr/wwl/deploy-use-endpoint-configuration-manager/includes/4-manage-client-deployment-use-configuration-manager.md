As we have seen from MDT, you can use Configuration Manager to create and deploy Windows images to devices. While many of the concepts are similar, Configuration Manager uses its own interface to manage the import and creation of boot images and the OS images. The deployment is handled through a combination of task sequences and target collections for which objects reside.<br>

#### Task Sequences

Configuration Manager task sequences work in a similar way to MDT task sequences, but they allow the flexibility to draw on other elements within it, such as application's created packages and scripts. In addition, you can integrate the Configuration Manager task sequence engine with the MDT binaries to offer greater flexibility around available options. Some of the scenarios for using a task sequence include:

 -  Deploying an operating system to a new or rebuilt device.
 -  Deploying a Windows upgrade.
 -  Capturing an operating system image for use in a deployment sequence.
 -  Capturing and restoring user state settings.
 -  Customizing a task sequence to carry out more advanced configurations.

#### Deployment Collections

After you have created the task sequence, you can target it at a deployment collection to enable successful delivery. This is a safety mechanism within Configuration Manager to prevent unintended delivery of an OS. You also have the option of targeting an in-built collection called **unknown computers**, which offers the flexibility of presenting any new device acquired with an ability to launch a created task sequence.

Collections help you organize resources into manageable units. Configuration Manager has built-in collections for common operations. You can also create custom collections to match your client management needs, and to perform operations on multiple resources at one time. Built-in and custom collections appear in the **User Collections** and **Device Collections** nodes in the **Assets and Compliance** workspace in the Configuration Manager console. Collections that you have recently viewed appear in the **Users** node and in the **Devices** node in the **Assets and Compliance** workspace.

By default, Configuration Manager includes the following built-in collections. These built-in collections can NOT be modified.

:::row:::
  :::column:::
    **Built-in collection name**
  :::column-end:::
  :::column:::
    **Description**
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All User Groups
  :::column-end:::
  :::column:::
    Contains the user groups that are discovered by using Active Directory Security Group Discovery.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All Users
  :::column-end:::
  :::column:::
    Contains the users who are discovered by using Active Directory User Discovery.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All Users and User Groups
  :::column-end:::
  :::column:::
    Contains the All Users and the All User Groups collections. This collection contains the largest scope of user and user group resources.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All Desktop and Server Clients
  :::column-end:::
  :::column:::
    Contains the server and desktop devices that have the Configuration Manager client installed. Membership is maintained by Heartbeat Discovery.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All Mobile Devices
  :::column-end:::
  :::column:::
    Contains the mobile devices that are managed by Configuration Manager. Membership is restricted to those mobile devices that are successfully assigned to a site or discovered by the Exchange Server connector.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All Systems
  :::column-end:::
  :::column:::
    Contains the All Desktop and Server Clients, the All Mobile Devices, and the All Unknown Computers collections, and all mobile devices that are enrolled by Microsoft Intune. This collection contains the largest scope of device resources.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    All Unknown Computers
  :::column-end:::
  :::column:::
    Contains generic computer records for multiple computer platforms. You can use this collection to deploy an operating system by using a task sequence and PXE boot, bootable media, or prestaged media.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Co-management Eligible Devices
  :::column-end:::
  :::column:::
    Contains devices that meet the client prerequisites and are eligible for co-management enrollment (added in version 2111).
  :::column-end:::
:::row-end:::


> [!TIP]
> Most management tasks rely on or require using one or more collections. Although you can use the built-in collection of **All Systems**, using it for management tasks isn't a best practice. Instead, you should create custom collections to more specifically identify the devices or users for a task.

### Troubleshooting a Windows Deployment using Configuration Manager

When delivering Windows with Configuration Manager through task sequences, you may be asked to provide either statistical analysis on success rates or require an ability to do some troubleshooting. Given this is such a complex and technical process, it is inevitable something may go wrong. The following sections describe some additional troubleshooting options.

#### Report

With a reporting services point configured in Configuration Manager, you can access to a set of tools and resources that help you use the advanced reporting capabilities of SQL Server Reporting Services (SSRS) and Power BI Report Server. Both reporting platforms provide rich analysis experiences for custom reports. Reporting helps you gather, organize, and present information about the wealth of Configuration Manager data in your organization. Configuration Manager provides many predefined reports in Reporting Services that you can use without changes. You can duplicate and modify the default reports to meet your requirements, or you can create custom reports.

#### Log Files

Configuration Manager produces numerous log files on both the client and server side to aid with troubleshooting. From a client perspective during the OS deployment phase, these move several times depending on the Windows Phase, but most of the time these will be located at C:\\Windows\\CCM\\Logs. Within this directory are several log files for helping to understand any issues that the client currently has. Some examples include the following:

 -  **Ccmsetup.log**. Responsible for the client setup, upgrade, and removal.
 -  **SMSTS.log**. Responsible for a lot of the initial logging during an OS deployment prior to Windows and the Configuration Manager client being fully installed.
 -  **AppEnforce.log**. Responsible for showcasing application installation information.
 -  **Execmgr.log**. Responsible for showcasing package installation information and script execution.

You can also use SetupDiag from Configuration Manager to help analyze and report on issues you may encounter during a Windows upgrade or deployment. For more information on SetupDiag, please visit [SetupDiag](/windows/deployment/upgrade/setupdiag).

> [!TIP]
> A good practice is to review the SRS Reports for task sequences and review the Deployment Status report for a given task sequence. This review can act as a starting point for troubleshooting which device went wrong and where it is located.

> [!TIP]
> CMTrace is your friend for reading and interpreting logfiles. You will never look at Notepad in the same way again.
