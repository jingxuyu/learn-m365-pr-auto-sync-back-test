Besides protecting resources such as devices, documents, and other critical types of data, it’s necessary to protect user identities, as well. Most of today’s successful cyber attacks are based on identity theft. This makes identity protection, especially of user accounts that have privileges, very important for organizations of all sizes.

Each computer user today has at least five, and very often more than five, identities (or accounts) for accessing different local or internet-based resources. For example, a typical user has personal accounts with Microsoft, Google, or Apple for emails; social accounts on Facebook and Twitter; and a business account on LinkedIn. Added to this, a typical information worker usually has one or more business accounts that they use on information systems in the organization where they work. Because of all this, a typical user must remember several sets of credentials to be able to access the personal and business resources that they use. This usually leads to a situation where most of the passwords for these accounts are similar or, in the worst case, even the same. This fact greatly increases the risk of identity theft. If one set of credentials is stolen or discovered in any way, it’s highly likely that the other identities of the same user will be at a severe risk.

Because of this, it’s necessary to have an identity protection strategy in each organization. Identity protection is a set of technologies that you implement in your organization that help you to proactively monitor user behavior, especially during authentication, and to take actions if risk or vulnerability is detected.

Azure AD Identity Protection is a Microsoft implementation of identity protection technology targeted at users of Microsoft 365 and other Microsoft cloud services. It’s a feature of the Azure AD Premium P2 license.

Azure AD Identity Protection provides you with the ability to:

 -  Proactively recognize potential security risks and identify vulnerabilities in your organization.
 -  Automatically apply responses and actions when suspicious activity on one or more identities is detected.
 -  Properly investigate incidents and take actions to resolve them.

You should not consider Azure AD Identity Protection as one more reporting and monitoring utility. With this technology, you can also define risk policies with clearly defined actions that can be taken manually or automatically.

Azure AD Identity Protection monitors each user session that authenticates on any of your cloud resources and calculates the potential risk. The risk is based on the user location, the application used to authenticate, the device the user uses, and other factors. For example, Azure AD Identity Protection can detect if the same user tries to authenticate from two very distant geographic locations in a short period of time. Also, it can detect if a user tries to authenticate from a location where he or she has never authenticated before.

:::image type="content" source="../media/azure-identity-protection-71fb80d4.png" alt-text="Screenshot of Azure AD Identity Protection remediation.":::


Based on a calculated risk, Azure AD Identity Protection can notify administrators, try to remediate the risk, increase the authentication security requirements, or take another action defined by the risk policy. The sign-in risk level can be Low and above, Medium and above, and High. For each risk level, you can define actions, such as require multi-factor authentication for signing-in, requiring password change, or blocking access.

Azure AD Identity Protection provides you with a dashboard where you can monitor, in real time, which users are flagged for risk, how many risk events have happened, and the potential vulnerabilities in your organization.
