>[!IMPORTANT]
>Threat protection product names in Microsoft are changing. [Read more about this and other updates](https://www.microsoft.com/security/blog/?p=91813). We'll be updating names in products and in the Learn content in the near future.

*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders. With the growing complexity of attacks, it's even more difficult for trained users to identify sophisticated phishing messages. Fortunately, EOP and the additional features in ATP can help.

## Anti-phishing protection in EOP
EOP (that is, for Microsoft 365 organizations without ATP) contains features that help protect your organization from phishing threats:
- **Spoof intelligence**: Reviews spoofed messages from senders in internal and external domains, and allows or blocks those senders.

   :::image type="content" source="../media/spoof-report.png" alt-text="A screenshot of a spoof report" border="true":::

- **Anti-phishing policies**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specifies the action for blocked spoofed senders (move to Junk Email folder or quarantine). 
- **Implicit email authentication**: Enhances standard email authentication checks for inbound email with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.

>[!NOTE]
> Many phishing attacks attempt to hide the actual sender and make the message appear as if it is from a trusted source. Messages from authenticated senders contain trackable sender identification to verify the source of their messages. Unauthenticated sender identification identifies senders that are not authenticated.

## Additional anti-phishing protection in Office 365 ATP
Office 365 ATP contains additional and more advanced anti-phishing features:
- **ATP anti-phishing policies**: Creates new custom policies and configures anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.
- **Campaign views**: Uses machine learning and other heuristics to identify and analyze messages that are involved in coordinated phishing attacks against one or many organizations.
- **Attack simulator**: Allows admins to create fake phishing messages and send them to internal users as an education tool. 

## Learn more
- [Anti-phishing protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-phishing-protection?view=o365-worldwide?azure-portal=true)
- [Anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies?view=o365-worldwide?azure-portal=true)
