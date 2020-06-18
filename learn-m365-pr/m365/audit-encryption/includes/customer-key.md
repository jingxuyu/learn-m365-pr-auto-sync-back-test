> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yvH4]

Customer Key is a feature that enables compliance with internal policies or compliance obligations involving the keys used for data encryption. These compliance obligations may include requirements to own the root keys used for data encryption, rotate keys on a defined cadence, or store keys in an HSM. Customer Key also provides customers the option to revoke their root keys and request a data purge when they leave the service, which shortens the time their data is retained in the cloud after service termination by cryptographically shredding the data, as outlined in the Online Services Terms.

When using Customer Key, the customers’ root keys leverage FIPS 140-2 compatible algorithms and do not leave the HSM boundary. As a result, customers may exercise their control and revoke their keys should they decide to exit the service. Revoking the keys and requesting a data purge renders encrypted data unreadable to our services.

The benefits of using Customer Key include:

- Providing rights protection and management features on top of strong encryption protection.
- Including Customer Key options that enable multi-tenant services to provide per-tenant key management.
- Protecting Windows operating system administrators from accessing customer data stored or processed by the operating system.
- Enhancing the ability of Microsoft 365 to meet the demands of customers with compliance requirements regarding encryption.

![Two flow diagrams depicting the Microsoft Customer Key hierarchy. The diagram to the left depicts the key hierarchy for Exchange Online, which shows how two Customer root RSA keys and one equivalent AES-256 availability key are used to protect the Data Encryption Policy Key, which in turn protects the Mailbox Key used to encrypt mailboxes in Exchange Online. The diagram to the right depicts the Customer Key hierarchy for SharePoint Online, OneDrive for Business, and Microsoft Teams files, which shares the same root and availability key configuration but uses these keys to protect a Tenant Intermediate Key, which in turn protects a Site Encryption Key, which is used to protect File Chunk Encryption Keys for encrypting customer data.](../media/customer-key.png)

## Availability key

For customers who use the Customer Key feature, Microsoft 365 provides data recovery capabilities using availability keys. The primary purpose of the availability key is to provide recovery capability from the unanticipated loss of customer managed root keys, including key loss from mismanagement or malicious action. If customers lose control of their root keys, Microsoft Support can support the process of recovery using the availability key.

The availability key is a root key provisioned and protected by Microsoft, which is functionally equivalent to the root keys supplied by the customer using the Customer Key feature. The availability key is automatically generated and provisioned when customers create a data encryption policy. By design, no one at Microsoft has access to the availability key: it is only accessible by Microsoft 365 service code. Microsoft 365 stores and protects the availability key, and unlike the keys that customers provide and manage in Azure Key Vault, customers cannot directly access the availability key. Nevertheless, Microsoft provides customers with sole authority over the disablement or destruction of the availability key. The availability key is unique to Customer Key, and should the customer decide to exit the service, the availability key is purged as part of the data purge process.

In addition to data recovery, the availability key can also be used to maintain service availability in Exchange Online. Although service failures are rare, transient AAD or network issues can threaten the availability of Microsoft 365 content. As a result, if Exchange Online cannot reach the customer’s root keys and we do not receive a response that indicates the customer has intended to block access to their root keys, the service falls back to the availability key to complete the operation. This rule only applies to Exchange Online. SharePoint Online and Microsoft Teams do not use the availability key unless the customer explicitly instructs Microsoft to initiate the recovery process.

Microsoft protects availability keys in access-controlled, internal secret stores, such as the customer-facing Azure Key Vault. We implement access controls to prevent Microsoft administrators from directly accessing the secrets contained within these vaults. Secret Store operations, including key rotation and deletion, occur through automated commands that do not involve direct access to the availability key. Secret store management operations are limited to specific engineers and require privilege escalation through Lockbox. Privilege escalation requires manager approval and justification before access can be granted. Lockbox ensures access is time bound with automatic access revocation when the time period expires.

## Learn more

- [Encryption for Skype for Business, OneDrive for Business, SharePoint Online, and Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-for-skype-onedrive-sharepoint-and-exchange?view=o365-worldwide&azure-portal=true)
- [Service encryption with Customer Key](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview?view=o365-worldwide&azure-portal=true)
- [Learn about the availability key for Customer Key](https://docs.microsoft.com/microsoft-365/compliance/customer-key-availability-key-understand?view=o365-worldwide&azure-portal=true)
- [Online Services Terms (OST)](https://aka.ms/OST?azure-portal=true)
