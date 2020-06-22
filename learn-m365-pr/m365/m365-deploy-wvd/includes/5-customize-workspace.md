Now that we've deployed a desktop and remote application to a workspace, let's customize the workspace and see how to configure RDP settings. We'll then install Windows Virtual Desktop Client for Windows to see how to access the workspace directly from your device.

To complete the exercise, you'll need the credentials for the user account that you assigned to the RemoteApp application group.

## Change the name of your workspace

1. [Sign in](https://portal.azure.com/learn.docs.microsoft.com?azure-portal=true) to the Azure portal.
1. Use the search box to find **Windows Virtual Desktop**.
1. Select **Workspace**.
1. Select the workspace you want to customize.
1. Under **Settings**, select **Properties**.
1. Update the **Friendly name**.

   :::image type="content" source="../media/5-workspace-properties.png" alt-text="Screenshot that shows workspace properties with the friendly name Contoso workspace.":::

## Change the name of your virtual desktops

1. In **Windows Virtual Desktop**, select **Application groups**.
1. Select the application group you want to customize.
1. Under **Settings**, select **Properties**.
1. Update the **Friendly name**.

   :::image type="content" source="../media/5-appgroup-properties.png" alt-text="Screenshot that shows the RemoteApp application group properties with the friendly name Costoso apps.":::

## Configure RDP properties 

1. In **Windows Virtual Desktop**, select **Host pools**.
1. Select the host pool you want to configure.
1. Under **Settings**, select **Properties**.
1. Select **RDP Settings**.
1. When you're done, select **Save**.

   :::image type="content" source="../media/5-hostpool-settings-rdp.png" alt-text="Screenshot that shows the RDP settings that are available on the host pool's properties.":::

## Install the Windows Virtual Desktop Client for Windows

In the previous units, we used the browser to connect to the Windows Virtual Desktop workspace. Now we'll install and run the Windows Virtual Desktop client directly from your device.

1. [Download the Windows Virtual Desktop Client](https://aka.ms/wvd/clients/windows) and install it.
1. Launch the Windows Virtual Desktop client  app.

   :::image type="content" source="../media/5-wvd-app-get-started.png" alt-text="Screenshot of the remote desktop window with the subscribe with URL button.":::

1. Select **Subscribe with an alternate URL**.
1. Enter the URL https://rdweb.wvd.microsoft.com/api/arm/feeddiscovery.
 
    :::image type="content" source="../media/5-subscribe-workspace.png" alt-text="Screenshot of the subscribe to workspace form with the URL pasted in.":::
1. Select Next.
1. Use the sign-in credentials for the account that has the RemoteApp application group assigned.
1. You should see the app you added to the RemoteApp application group.

   :::image type="content" source="../media/5-remote-desktop-workspace.png" alt-text="Screenshot of the contoso workspace with the WordPad app available.":::
