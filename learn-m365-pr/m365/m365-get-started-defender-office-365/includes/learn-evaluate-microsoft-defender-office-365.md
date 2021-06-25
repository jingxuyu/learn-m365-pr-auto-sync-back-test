The Microsoft Defender for Office 365 evaluation mode is a simplified instance of Microsoft Defender for Office 365 that lets you evaluate the essential capabilities, without having to go through all of the setup steps. Which lets you focus on evaluation of the essential capabilities.  The only features and functions enabled in the evaluation version are those that support email protection.

You have two choices when it comes to deciding how to evaluate Microsoft Defender for Office 365. The first way is to use your existing tenant. However, you’ll need to make sure you have a suitable license.  The other is to start a 30-day evaluation trial where you’ll be able to test the capabilities of Office 365 Security and Compliance center.

To run an evaluation from your existing tenant, you'll need any of the following licenses.

- Microsoft Defender for Office 365 Plan 1
- Microsoft Defender for Office 365 Plan 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

You're concerned that running a trial using an existing license could impact your existing services. Since you're only evaluating the product, you decide to use the 30-day trial version.

To obtain the 30-day trial license, you’ll need to go to the Microsoft 365 security portal.

1. Select **Email & Collaboration**
1. Then select **Policies and Rules**
1. Now select **Threat Policies**
1. Then choose **Additional Policies**

## Getting Started with the evaluation

To get started with the trial evaluation, launch the [Office 365 Security & Compliance portal](https://protection.office.com/homepage).  

There are three ways you can find the Defender for Office 365 evaluation setup up card.

:::image type="content" source="../media/2-defender-office-card.png" alt-text="Fragment of a screenshot, showing the Defender for Office 365 evaluate card.":::

From the navigation pane on the left-hand side, you can select either:

- **Threat management** > **Dashboard**
- **Threat management** > **Policy**
- **Reports** > **Dashboard**

Once you have found the card, to get started with the evaluation, select **Evaluate**.

## Setting up the evaluation

Now that you’ve launched the evaluation setup. The wizard will guide you through what you need to do. There are a few things you’ll need to consider as you run through the setup wizard:

- You’ll need to make a choice on which routing option you want. This will be governed by the mail routing setup you currently have, and also on the type of evaluation you want to run.
  - If you're using a third-party and/or on-premises service provider:
    - Select the name of the vendor from the drop-down menu.
    - Provide the other connector-related details.
  - If you're using an Exchange Online mailbox:
    - Select **Microsoft Exchange Online**

When you're ready, you should take a moment to review your settings and edit them if necessary. Then select **Create evaluation**. You should get a confirmation message to indicate that your set-up is complete.

By default, when you start using Microsoft Defender for Office 365 in evaluation mode, the following things are set up:

- Email policies are created that log verdicts such as malware but these policies won't act on a message.
- Safe Links, Safe Attachments, and mailbox intelligence-based impersonation policies are created.
- Policies created in evaluation mode are done so in non-enforcement mode.
- Enhanced Filtering for Connectors are set up, which improves the filtering accuracy.

When the evaluation mode is set up, you'll have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented. It can take up to 24 hours for the data to populate.

## Evaluation report

From the report you can see how many advanced threat links, advanced threat attachments, and potential impersonations were identified. Data will be collected from both emails and collaboration workspaces.

> [!NOTE]
> At any time during the evaluation period, you can go to settings and update your routing or turn off your evaluation.

## Video Guide

For a more in-depth introduction to Microsoft Defender for Office 365 evaluation mode and how you can get the best out of your evaluation, you should watch this 20-minute video.

[![Evaluation mode video](../media/2-evaluation-mode-video.png)](https://www.microsoft.com/videoplayer/embed/RWEmVP?azure-portal=true)
