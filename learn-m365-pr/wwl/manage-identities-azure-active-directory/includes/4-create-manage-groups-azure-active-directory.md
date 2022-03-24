Like using groups to simplify permissions management in AD DS, you can use groups in Azure AD to simplify management. If you implement directory synchronization, groups in your on-premises AD DS can synchronize with Azure AD. A synchronized group in Azure AD has the same membership as the group in AD DS, but the individual members are translated from on-premises user accounts to user accounts in Azure AD. Alternatively, if you don’t implement directory synchronization, then groups and their membership are managed entirely in the cloud.

You can create four group types in Azure AD:

 -  **Security**. You can use this type of group to assign permissions, but you can’t use it to send emails.
 -  **Mail-enabled security**. You can use this type of group to assign permissions, and you can send emails to members.
 -  **Distribution**. You can use this type of group to send emails to members, but you can’t assign permissions.
 -  **Office365 groups**. You can use this type of group to enable collaboration for members. You can email an office group, and it will store a copy of those emails. It also has storage space in SharePoint Online for files.

On the Azure portal, you can only create security groups and office groups. Other group types display on the Azure portal and can be managed on the Azure portal, but can’t be created on the Azure portal. You can create mail-enabled security groups and distribution groups in the Microsoft 365 portal.

#### Assign Membership

Membership for a cloud-based group can be **assigned** or **dynamic**. When you create a group with assigned membership, you need to add and remove group members manually. When you create a group with dynamic membership, members are based on a query of Azure AD objects. For example, dynamic membership can be based on a user’s department. You can create a simple membership rule based on a single attribute or an advanced membership rule where you can create complex queries based on multiple attributes.

When you create a group with dynamic membership, you need to select whether it’s for users or devices. Many Microsoft 365 features can use user-based groups. Intune uses device-based groups.

Groups from on-premises AD DS with dynamic membership don’t synchronize with Azure AD.
