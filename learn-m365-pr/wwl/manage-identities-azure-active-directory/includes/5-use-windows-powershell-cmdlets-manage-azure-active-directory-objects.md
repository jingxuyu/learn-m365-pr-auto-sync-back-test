You can also manage users, groups, and devices by using the Microsoft Azure Active Directory module for Windows PowerShell module. To run the Microsoft Azure Active Directory module for Windows PowerShell module, you need the following requirements:

 -  **Operating system**. You must be running either Windows 7 or newer, or Windows Server 2008 R2 or newer.
 -  **Microsoft .NET Framework**. You must install the Microsoft .NET Framework 3.51 feature.
 -  **Software updates**. You must have installed all the updates required by the Microsoft cloud services to which you've subscribed.
 -  **Microsoft Online Services Sign-in Assistant**. You must install the appropriate version of the Microsoft Online Services Sign-in Assistant for your operating system from the Microsoft Download Center.

To connect to Azure AD, at the Microsoft Azure Active Directory module for Windows PowerShell prompt, type the following command, and then select **Enter**:

```
Connect-MsolService

```

You're then prompted for administrator credentials. Once you provide your administrator credentials, you’re ready to execute cmdlets for Azure AD.

#### Create users by using bulk import

To create multiple users in bulk, you can either import a .csv file containing account information, such as exporting from an existing on-premises directory, or use Azure PowerShell scripting to generate multiple accounts. To use bulk import, you first must assemble your user information, which might include the following:

:::row:::
  :::column:::
    **UserName**
  :::column-end:::
  :::column:::
    **FirstName**
  :::column-end:::
  :::column:::
    **LastName**
  :::column-end:::
  :::column:::
    **DisplayName**
  :::column-end:::
  :::column:::
    **JobTitle**
  :::column-end:::
  :::column:::
    **Department**
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    AnneW@adatum.com
  :::column-end:::
  :::column:::
    Anne
  :::column-end:::
  :::column:::
    Wallace
  :::column-end:::
  :::column:::
    Anne Wallace
  :::column-end:::
  :::column:::
    President
  :::column-end:::
  :::column:::
    Management
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    FabriceC@adatum.com
  :::column-end:::
  :::column:::
    Fabrice
  :::column-end:::
  :::column:::
    Canel
  :::column-end:::
  :::column:::
    Fabrice Canel
  :::column-end:::
  :::column:::
    Attorney
  :::column-end:::
  :::column:::
    Legal
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    GarretV@adatum.com
  :::column-end:::
  :::column:::
    Garret
  :::column-end:::
  :::column:::
    Vargas
  :::column-end:::
  :::column:::
    Garret Vargas
  :::column-end:::
  :::column:::
    Operations
  :::column-end:::
  :::column:::
    Operations
  :::column-end:::
:::row-end:::


You then need to create a .csv file in the following format:

```
UserName,FirstName,LastName,DisplayName,JobTitle,Department
AnneW@adatum.com,Anne,Wallace,Anne Wallace,President,Management
FabriceC@adatum.com,Fabrice,Canel,Fabrice Canel,Attorney,Legal
GarretV@adatum.com,Garret,Vargas,Garret Vargas,Operations,Operations
```

You can then use Microsoft Azure Active Directory module for Windows PowerShell commands to process this .csv file and create the user accounts as shown below:

```
$users = Import-Csv C:\Users.csv

$users = Import-Csv C:\Users.csv

$users | ForEach-Object {

New-MsolUser -UserPrincipalName $_.UserName -FirstName $_.FirstName -LastName
$_.LastName -DisplayName $_.DisplayName -Title $_.JobTitle -Department
$_.Department

}

```
