Depending on your needs, you can use the following methods to provision user accounts:

 *  **Microsoft 365 admin center.** This poratal provides a simple web interface for individually creating and managing users. Is also available as an app for mobile devices or tables as Microsoft 365 admin app.
 *  **Import multiple users.** This option provides a method for the bulk importation of multiple users into the Microsoft 365 admin center through a comma-separated value (CSV) file.
 *  **Windows PowerShell.** You can use this cmdlet-based and script-based interface to create and manage single and multiple users.
 *  **Directory synchronization.** This option requires you to provision and manage users by synchronizing Microsoft 365 with an on-premises directory service such as Active Directory. You can use the Azure AD Connect tool to synchronize on-premises Active Directory objects with Azure AD in Microsoft 365.

The most common and easiest way to create user accounts in non-directory synchronized environments is to use the Microsoft 365 admin center or the Microsoft 365 admin app. More advanced methods such as importing multiple users or Windows PowerShell are normally used for mass-imports, or if you implemented an automated script for user creation. In environments where you implemented directory synchronization, you cannot use the Microsoft 365 admin center or Windows PowerShell for user creation, but you instead must use the local tools available in your Active Directory.

### Creating users with the Microsoft 365 admin center

Using the Microsoft 365 admin center is the simplest method for creating one or more user accounts. To create a user, following these steps:

1.  Sign in to Microsoft 365 admin center.
2.  On the **Microsoft 365 admin center**, in the left-hand navigation pane, select the **Users** group and then select **Active users.**
3.  On the **Active users** page, select **Add a user**. This action will initiate a wizard that walks you through the steps necessary to add the user information.
4.  On the **Set up the basics** page, enter the required user and password information. Verify you select the correct domain for the Username.
5.  On the **Assign product licenses** page, select the product license(s) that should be assigned to the user.
6.  On the **Optional settings** page, select the role(s) you want to assign to this user.
7.  On the **Review and finish** page, review the information you entered, and if necessary, correct any information that was entered incorrectly. When all information is correct, select the **Finish adding** button to add the user account.

### Creating users with the Import multiple users option

You can use the **Add multiple users** option in the Microsoft 365 admin center to add large numbers of users in one operation by using a comma-separated values (CSV) file. Microsoft 365 provides an empty template and a sample CSV file to make the process easier. You can use a text-editing tool such as Notepad or Microsoft Excel to edit these files. To create users by using bulk import, you should perform the following steps:

1.  In the Microsoft 365 admin center, on the **Active users** page, select **Add multiple users**.
2.  Browse to the CSV file that contains your users.
3.  The verification result informs you if any errors are in your file. If there are errors, you can view the results in the linked log file.
4.  On the **Set user options** page, set the new users’ sign-in status, location, and licenses.
5.  On the **View your results** page, specify who should receive the email of the results. It is recommended that you include your own email address so that you can provide the temporary passwords to your new users.

### Creating users with Windows PowerShell

If you prefer to use Windows PowerShell rather than the Microsoft 365 admin center for performing user administrative functions, you can use the **New-MsolUser** cmdlet to create a user account in Microsoft 365.

```
New-MsolUser -UserPrincipalName username@domainname –DisplayName “Firstname Lastname” –FirstName “Firstname” –LastName “Lastname”
```

For example, the following cmdlet creates a user account for Patti Fernandez:

```
New-MsolUser –UserPrincipalName PattiF@Adatum.onmicrosoft.com –DisplayName “Patti Fernandez” – FirstName “Patti” –LastName “Fernandez”
```

This cmdlet can also assign a user license at the same time so that the user can start accessing online services. You can also directly assign a Microsoft 365 license during user creation by using the **-UsageLocation** and **-LicenseAssginment** parameters with the **New-MsolUser** cmdlet.

For example, the following cmdlet creates a user account for Patti Fernandez and assigns a Microsoft 365 Enterprise Premium (E5) license to the new account:

```
New-MsolUser –UserPrincipalName PattiF@Adatum.onmicrosoft.com –DisplayName “Patti Fernandez” – FirstName “Patti” –LastName “Fernandez” –UsageLocation “US” –LicenseAssignment “Adatum: ENTERPRISEPREMIUM”
```

## Knowledge check

Choose the best response for the following question. Then select “Check your answers.”