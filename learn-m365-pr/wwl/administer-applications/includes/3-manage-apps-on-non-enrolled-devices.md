There are many different ways that applications can be made available to your users today. They can be deployed from Intune either as Required or Available or users can directly install apps from public stores.

Apps that are that are installed directly from public stores are considered to be unmanaged and apps that are deployed by Intune to be managed. For managed apps, IT has direct control over deployment, ongoing management (such as inventory or updates), and selective wipe of the apps and their associated data. Most mobile devices have OS level controls in place to limit (containerize) the movement of data. Intune supports an additional level of management for managed apps that are integrated with the Intune App SDK or the Intune App Wrapping Tool. For these MAM protected apps, additional controls such as per-app PIN, jailbreak detection, and granular control over data flow can be added. Depending on the specific DLP requirements of your organization, you can choose the right mix of unmanaged, managed and MAM-protected applications for your users.

An unmanaged app is any app available on Windows, Android and iOS. Intune doesn’t have any control over the distribution, management, or selective wipe of these apps. Intune MAM provides additional capabilities to protect managed apps by offering an additional layer of data protection.

A managed app is an app for which Intune manages the whole lifecycle such as:

 -  Deploy the app
 -  Manage app updates
 -  Monitor app installation
 -  Selectively wipe the entire app

Intune also supports deploying apps to unenrolled devices. Currently, you can assign iOS and Android apps and iOS and Android built-in apps to devices that aren't enrolled in Intune.

#### **Updates for unenrolled devices**

To receive app updates on devices that aren't enrolled with Intune, device users must go to their organization's Company Portal and manually install app updates.

Users can then use either the Company Portal app or go to the Intune Company Portal website at [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) on any of their devices and install the application without needing the device to be enrolled in Intune. The Company Portal app will not prompt users to enroll their devices if the app is configured to not require enrollment.

#### **Deploy apps to unenrolled devices**

To deploy an app to an unenrolled device, perform the following steps:

1.  Sign in to the **Endpoint Administrator admin center**.
2.  Select **Apps**, then select **All Apps**.
3.  In the **All apps** view, select an existing application that support assignment to unenrolled devices.
4.  On the Overview page of the selected app, select **Properties**.
5.  On the **Properties** page, next to the **Assignments** section, select **Edit.**
6.  On the **Edit Application** page, under **Available with or without enrollment**, select **+Add Group** or **+Add all users**. You can select the groups to which you want to assign the app. You must choose a group which only contains users when assigning apps to unenrolled devices. You can also choose whether to make the app available to all users, regardless whether their devices are enrolled in Intune. This will assign the app to all users in Intune.
7.  Select **Review + Save** and then select **Save**.

You can easily make apps available on devices that cannot be enrolled in Intune and use app protection policies (MAM) to manage the apps after they have been installed. Even though this can be helpful in BYOD scenarios, we recommended that you always enroll your devices in Intune whenever possible and this will give you all of Intune´s management functionality.
