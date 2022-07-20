Microsoft Teams call parking and retrieve features enable an organization's users to place calls on hold. When a user parks a call, a unique code is generated that can be used to retrieve the call later down the line. 

Some of the common scenarios for using call parking include:

* A receptionist parks a call for someone working in a factory. The receptionist then announces the call and the code number over the public address system. The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.

* A user parks a call on a mobile device because the device battery is running out of power. The user can then enter the code to retrieve the call from a Teams desk phone.

* A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer. An expert enters the code in Teams clients to retrieve the call.

A Teams administrator can enable call parking and retrieve for users. A call park policy can also be created for user groups.

* Call park and retrieve is only available in **Teams Only** deployment mode. To set the deployment mode to **Teams only**, navigate to **Teams** > **Teams upgrade settings** in the Microsoft Teams admin center, and then set the **Coexistence** mode to **Teams only**.

* To park and retrieve calls, a user must be an Enterprise Voice user and included in a call park policy.

* When the same policy is applied to a set of users, they can park and retrieve calls among themselves.

## Create a call park policy

Call parking and retrieval can be enabled by first enabling a call park policy. Complete the following steps to enable a call park policy:

1. Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/?azure-portal=true).
2. In the left-hand navigation pane, select **Voice** > **Call park policies**.
3. Select **+ Add** on the **Manage policies** tab.
4. Provide a name for your policy, and then set **Call park** to **On**.
5. Select **Save**.

You can also use the ```New-CsTeamsCallParkPolicy``` PowerShell cmdlet to create a call park policy.

:::image type="content" source="../media/new-call-park-policy.png" alt-text="Screenshot of Create new call park policy.":::  

## Assign the policy to a group

For a call park policy to take effect, it must be assigned to users either on a per-user level or on a group-level. 

|Scenarios|Details|
|--|--|
|Assign a policy directly to an individual user| Go to **Users** > **Manage users** > Select a user > **Policies** tab > **Assigned policies**. |
|Assign a policy to a batch of users| Option 1: Go to **Users** > **Manage users** > Select multiple users > **Edit settings**. <br/>Option 2: Go to **Call park policies** > Select the policy > **Assign users**.|
|Assign a policy to a group| Go to **Call park policies** > **Group policy assignment** > **+Add** and follow the configuration. |
|Assign a policy package directly to an individual user.| Go to **Users** > **Manage users** > Select a user > **Policies** tab > **Policy package**. |
| Assign a policy package to a batch of users| Go to **Policy packages** > Select the policy package > **Manage users**.|
|Assign a policy package to a group| Go to **Policy packages** > **Group policy assignment** > **+Add** and follow the configuration. |



For example, you can complete the following steps to assign a call park policy to a group:

1. Select the **Group policy assignment** tab in the **Call park policies** pane.

	:::image type="content" source="../media/assigning-group-policy.png" alt-text="Screenshot of the Group policy assignment option.":::  

2. Select **Add**. The **Assign policy to group** pane appears.
3. In the **Select a group** field, look for your target group and select it.

	:::image type="content" source="../media/assign-policy-to-group.png" alt-text="Screenshot showing how to assign policy to a group.":::  

4. In the **Select rank** field, assign a rank you want to set for this group assignment compared with other assignments.
5. In the **Select a policy** field, select your newly created policy.
6. Select **Apply** to apply your policy to the group.

You can also use the  ```Grant-CsTeamsCallParkPolicy``` PowerShell cmdlet to grant a call park policy.

