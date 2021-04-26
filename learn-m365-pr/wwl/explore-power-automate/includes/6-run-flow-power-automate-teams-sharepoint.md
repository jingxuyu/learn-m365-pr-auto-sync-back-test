Once a flow is saved without errors, it's active and available to run when the trigger condition is satisfied. Button (instant) flows run when they're manually triggered.

### Running flows in Power Automate

Within Power Automate, users can view all their flows by selecting **My flows** from the flow designer page on the browser. Selecting the flow name presents the user with the Edit and Share icons, and an ellipsis that presents a more extensive list of options, such as turning off the flow.

The following list describes several of the key options that can be applied to a flow:

 *  **Run.** This option shows up on with certain types of flows, including instant flows and scheduled flows. Selecting run with a scheduled flow satisfies the trigger condition. For example, if a scheduled flow is scheduled to run at midnight, pressing run executes the flow even if the time condition hasn't been met.
 *  **Share.** Flows can be shared with other users either as co-owners or run-only users.
    
     *  **Co-owner.** When a user adds another user or group as an owner of a flow, that flow becomes a team flow (which only show up under Team flows) and provides those users with full access to all the connections used in the flow. Full access to all the connections means the flow takes action in the context of the user signed into the connection. ‎Co-owners of the flow can also modify the flow using the connections that already exist. They may also change the login on the connection; however, they're not required to do so. Co-owners are limited to use the connection with that flow. They can't create a new flow and use the same connection.
     *  **Run-only.** Run-only sharing is an option when the flow is manually triggered (button flows). Only the user to which the flow is shared can run it, and the user can't edit the flow. Run-only sharing can also be configured so that the user to which the flow is shared can reuse the existing connection or be required to provide their own connection.

If a flow containing a Microsoft 365 group is shared, the flow becomes available to all members of the group. When a flow containing a SharePoint List is shared, anyone with edit access to the list can access to the flow. The flow will then appear on the SharePoint navigation screen, where it can be selected to run.

 *  **Send a copy.** Sending a copy of a flow means that recipients can create their own copies of the original flow. These copies use the recipient’s connections and be owned by the recipient. To send a copy of the flow, the user sharing the flow must first ensure that it doesn't contain any personal information. For example, a flow that sends something to your email address would likely not be appropriate to send as a copy to others.
 *  **Export.** Flow owners can export a flow as a zip package, for import into a different environment.
 *  **Run history.** Run history provides a detailed history view, where you can click on a single flow run and see exactly which steps have succeeded or failed. A user can also download a CSV of the flow run history and use Excel (or any other tool) to search across all flow runs, see exactly when they happened, and view the inputs and outputs of most steps.
 *  **Analytics.** Flow Analytics provides flow makers with the ability to visualize their run history, including error details. Flow analytics can help to quickly identify the source and magnitude of errors encountered when the flow is executed. They can also aid in the prompt resolution of these errors.
 *  **Turn-off.** Toggle between turning the flow off/on. When you create a flow and successfully save it, the flow is on by default. Users must explicitly turn it off.
 *  **Repair tips.** Repair tips are sent to flow owners via email whenever a flow fails. These repair tips emails contain specific, actionable feedback about certain errors.

### Running flows in SharePoint

A flow can be executed from within SharePoint when a flow containing a SharePoint List is shared. Anyone with edit access to the SharePoint list has access to the flow, and the flow would then show up with the ability to be executed from the SharePoint navigation screen.

### Running flows in Teams

Users can create, manage, and run flows from within Microsoft Teams:

From the Teams navigation page of Teams, users can select the option to display apps, and form the apps list they can select Flow.

When the user selects the Flow app, the following tabs are displayed:

 *  **Conversation.** Enables users to interact with the Flow bot. Users can send commands to the Flow bot, which responds by completing the specified action. For example:
    
     *  **List flows.** The bot displays a list of your flows, prefixed by an index number.
     *  **Describe flow 1.** Describes the flow whose index number is 1.
     *  **Run flow 1.** Runs the flow whose index number is 1.
 *  **Flows.** This tab opens up Power Automate directly in Teams, which enables users to create and manage flows.
 *  **Approval.** Displays received and sent approvals requests. The following subtabs are available:
    
     *  **Received.** Displays approval requests that have been received and are pending action from you.
     *  **Sent.** Displays approval requests that have been sent and are pending action from others.
     *  **History.** Displays received and sent approval requests.
     *  **Create approval flow.** Opens Power Automate and enables users to create approval flows.
 *  **About.** Displays version and other information about Power Automate.

### Running flows in the Power Automate mobile phone app

Power Automate flows can be created, managed, and run from the Power Automate mobile phone app.

 *  **Buttons.** Selecting the Buttons tab on the phone app displays button flows the user owns, and flows that have been shared with that user. Users can run the flow simply by tapping on the flow button. Selecting the ellipsis presents the option to invite others or share the button link.
 *  **Flows.** Selecting the Flows tab displays the list of “My flows”, “Team flows”, and “UI flows (preview)”, all of which are consistent with what the user would see from the browser. Selecting any flow on the list displays the available options supported for that flow, including the ‘Run now’ option.
