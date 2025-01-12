Investigating risky user activities is an important first step in minimizing insider risks for an organization. These risks may be:

 -  Activities that generate alerts from insider risk management policies.
 -  Risks from activities that are detected by policies but don't immediately create an insider risk management alert for users.

Organizations can investigate these types of activities by using the **User activity reports** and the **Alert** dashboard.

### User activity reports

User activity reports allow an organization to examine activities for specific users for a defined time period. The organization can view the reports without having to temporarily or explicitly assign the users to an insider risk management policy. In most insider risk management scenarios, users are explicitly defined in policies. They may also have policy alerts (depending on triggering events) and risk scores associated with the activities.

But in some scenarios, they may want to examine the activities for users that aren't explicitly defined in a policy. These activities may be for users they've received a tip about who participate in potentially risky activities. They may also be for users who typically don't need to be assigned to an insider risk management policy.

After an organization has configured indicators on the insider risk management **Settings** page, user activity is detected for risky activity associated with the selected indicators. The organization doesn't have to configure a policy for user activity reports to detect and report risky activities by its users. Activities included in user activity reports don't require triggering events for the activities to be displayed.

This configuration means that all detected activity for the user is available for review. The activities don't require a triggering event, and they don't need to create an alert. Reports are created on a per-user basis and can include all activities for a custom 90-day period. Multiple reports for the same user aren't supported.

After investigators examine activities for a user, they can:

 -  Dismiss individual activities as benign.
 -  Share or email a link to the report with other investigators.
 -  Choose to assign the user temporarily or explicitly to an insider risk management policy.

Users must be assigned to the **Insider Risk Management Investigators** role group to view the **User activity reports** page.

:::image type="content" source="../media/insider-risk-user-activity-report-overview-cab556cd.png" alt-text="Screenshot of the Insider risk management user activity reports page showing multiple user activity reports." lightbox="../media/insider-risk-user-activity-report-overview-cab556cd.png":::


An organization can get started by selecting **Manage reports** in the **Investigate user activity** section on the insider risk management **Overview** page. To view activities for a user, first select **Create user activity report**. Then complete the following fields in the **New user activity report** pane:

 -  **User**. Search for a user by name or email address.
 -  **Start date**. Use the calendar control to select the start date for user activities.
 -  **End date**. Use the calendar control to select the end date for user activities. The end date selected must be greater than two days after the selected start date, and not greater than 90 days from the selected start date.

> [!NOTE]
> New reports typically take up to 10 hours before they're ready for review. When the report is ready, you'll see **Report ready** in the **Status** column on the **User activity report** page. Select the user to view the detailed report.

:::image type="content" source="../media/insider-risk-user-activity-report-85fabbe6.png" alt-text="Screenshot of the Insider risk management user activity report showing all the user activity for a selected report." lightbox="../media/insider-risk-user-activity-report-85fabbe6.png":::


The **User activity report** for the selected user contains the **User activity** and **Activity explorer** tabs:

 -  **User activity**. Use this chart view to investigate activities and view potential activities that occur in sequences. This tab is structured to enable quick review of a case, including:
     -  a historical timeline of all activities.
     -  activity details.
     -  the current risk score for the user in the case.
     -  the sequence of risk events.
     -  filtering controls to help with investigative efforts.
 -  **Activity explorer**. The Activity explorer tab provides risk investigators with a comprehensive analytic tool that provides detailed information about activities. With the Activity explorer, reviewers can quickly review a timeline of detected risky activity and identify and filter all risk activities associated with alerts.

### Alert dashboard

Insider risk management alerts are automatically generated by risk indicators defined in insider risk management policies. These alerts give compliance analysts and investigators an all-up view of the current risk status. They also enable an organization to triage and take actions for discovered risks. By default, policies generate a certain amount of low, medium, and high severity alerts. However, an organization can increase or decrease the alert volume to suit its needs. It can also configure the [alert threshold for policy indicators](/microsoft-365/compliance/insider-risk-management-settings?azure-portal=true) when creating a new policy with the policy creation tool.

**Additional viewing**. For an overview of how alerts provide details, context, and related content for risky activity and how to make the investigation process more effective, select the following link to watch a short video titled: [Insider Risk Management Alerts Triage Experience](https://www.youtube.com/watch?v=KgmpxBLJLPI).

The insider risk Alert dashboard enables organizations to view and act on alerts generated by insider risk policies. Each report widget displays information for the last 30 days, including:

 -  **Total alerts that need review**. The total number of alerts needing review and triage are listed, including a breakdown by alert severity.
 -  **Open alerts over past 30 days**. The total number of alerts created by policy matches over the last 30 days, sorted by high, medium, and low alert severity levels.
 -  **Average time to resolve alerts**. A summary of useful alert statistics:
     -  Average time to resolve high severity alerts, listed in hours, days, or months.
     -  Average time to resolve medium severity alerts, listed in hours, days, or months.
     -  Average time to resolve low severity alerts, listed in hours, days, or months.

:::image type="content" source="../media/insider-risk-alerts-dashboard-3176fd13.png" alt-text="Screenshot of the Insider risk management dashboard showing the Alerts tab.":::


> [!WARNING]
> Insider risk management uses built-in alert throttling to help protect and optimize an organization's risk investigation and review experience. Throttling guards against issues that may result in an overload of policy alerts. For example, misconfigured data connectors or DLP policies. As a result, there might be a delay in displaying new alerts for a user.

### Alert status and severity

Organizations can triage alerts into one of the following statuses:

 -  **Confirmed**. An alert confirmed and assigned to a new or existing case.
 -  **Dismissed**. An alert dismissed as benign in the triage process. You can provide a reason for the alert dismissal and include notes that are available in the user's alert history. Doing so provides extra context for future reference or for other reviewers. For example, the reasons could include:
     -  Expected activities
     -  Non-impactful events
     -  Reducing the number of alert activities for the user
     -  A reason related to the alert notes. Reason classification choices include:
         -  **Activity is expected for this user.**
         -  **Activity is impactful enough for me to investigate further.**
         -  **Alerts for this user contain too much activity.**

 -  **Needs review**. A new alert where triage actions haven't yet been taken.
 -  **Resolved**. An alert that's part of a closed and resolved case.

Alert risk scores are automatically calculated from several risk activity indicators. These indicators include:

 -  The type of risk activity.
 -  The number and frequency of the activity occurrence.
 -  The history of user risk activity.
 -  The addition of activity risks that may boost the seriousness of the activity.

The alert risk score drives the programmatic assignment of a risk severity level for each alert. It can't be customized. If alerts remain untriaged and risk activities continue to accrue to the alert, the risk severity level can increase. Risk analysts and investigators can use alert risk severity to help triage alerts in accordance with their organization's risk policies and standards.

Alert risk severity levels include:

 -  **High severity**. The activities and indicators for the alert pose significant risk. The associated risk activities are serious, repetitive, and corelate strongly to other significant risk factors.
 -  **Medium severity**. The activities and indicators for the alert pose a moderate risk. The associated risk activities are moderate, frequent, and have some correlation to other risk factors.
 -  **Low severity**. The activities and indicators for the alert pose a minor risk. The associated risk activities are minor, more infrequent, and don't corelate to other significant risk factors.

Investigating risky user activities is an important first step in minimizing insider risks for an organization. These risks may be activities that generate alerts from insider risk management policies. Or, they may be risks from activities that are detected by policies but don't immediately create an insider risk management alert for users. You can investigate these types of activities by using the **User activity reports** or with the **Alert** dashboard.

### Triage alerts

To triage an insider risk alert, complete the following steps:

1.  In the **Microsoft Purview compliance** portal, select **Insider risk management** in the navigation pane.
2.  On the **Insider risk management** page, select the **Alerts** tab.
3.  On the **Alerts** dashboard, select the alert you want to triage.
4.  On the **Alert detail** page, you can review information about the alert. You can:
     -  Confirm the alert and create a new case.
     -  Confirm the alert and add to an existing case.
     -  Dismiss the alert.

    The **Alert detail** page also includes the current status for the alert and the alert risk severity level, listed as High, Medium, or Low. The severity level may increase or decrease over time if the alert isn't triaged.

### Activity explorer

> [!NOTE]
> When Activity explorer is available in an organization, the alert management area for users with triggering events will be available.

The Activity explorer provides risk investigators and analysts with a comprehensive analytic tool that provides detailed information about alerts. With the Activity explorer, reviewers can quickly review a timeline of detected risky activity and identify and filter all risk activities associated with alerts.

To filter alerts on the Activity explorer for column information, select the **Filter** control. Alerts can be filtered by one or more attributes listed in the details pane for the alert. Activity explorer also supports customizable columns to help investigators and analysts focus the dashboard on the information most important to them.

An organization can use the **Activity scope** and **Risk insight** filters to display and sort activities and insights for the following areas:

 -  **Activity scope filters**. Filters all scored activities for the user.
     -  All scored activity for this user.
     -  Only scored activity in this alert.
 -  **Risk factor filters**. Filters for risk factor activity applicable for all policies assigning risk scores This includes all activity for all policies for in-scope users.
     -  Unusual activity
     -  Includes events with priority content
     -  Includes events with unallowed domain
     -  Sequence activities
     -  Cumulative exfiltration activities
     -  Health record access activities

:::image type="content" source="../media/insider-risk-activity-explorer-71becff0.png" alt-text="Screenshot showing the Insider risk management activity explorer page for a specific case and with selected filters.":::


To use the Activity explorer, complete the following steps:

1.  In the **Microsoft Purview compliance** portal, select **Insider risk management** in the navigation pane.
2.  On the **Insider risk management** page, select the **Alerts** tab.
3.  On the **Alerts** dashboard, select the alert you want to triage.
4.  On the **Alerts detail** pane, select **Open expanded view**.
5.  On the page for the selected alert, select the **Activity explorer** tab.

When investigators and analysts review activities in the Activity explorer, they can select a specific activity and open the activity details pane. The pane displays detailed information about the activity that investigators and analysts can use during the alert triage process. Detailed information may provide context for the alert. It may also assist with identifying the full scope of the risk activity that triggered the alert.

When investigators and analysts select an activity's events from the activity timeline, the number of activities displayed in Activity explorer may not match the number of activity events listed in the timeline. This difference may occur for the following reasons:

 -  **Cumulative exfiltration detection**. Cumulative exfiltration detection analyzes event logs. However, it applies a model that includes de-duplicating similar activities to compute cumulative exfiltration risk. There may also be a difference in the number of activities displayed in the Activity explorer if an organization made changes to its existing policy or settings. For example, if the organization modified allowed/unallowed domains or added new file type exclusions after a policy was created and activity matches occurred, the cumulative exfiltration detection activities will differ from the results before the policy or settings changes. Cumulative exfiltration detection activity totals are based on the policy and settings configuration at the time of computation. They don't include activities prior to the policy and settings changes.
 -  **Emails to external recipients**. Activity for emails sent to external recipients is assigned a risk score based on the number of emails sent. This value may not match the activity event logs.

:::image type="content" source="../media/insider-risk-activity-explorer-details-1b0d008c.png" alt-text="Screenshot showing the Insider risk management activity explorer page for a specific case and a flyout of the activity details.":::


## Knowledge check

Choose the best response for the following question. Then select “Check your answers.”