---
author: DanWahlin
ms.author: dwahlin
ms.date: 02/23/2022
ms.prod: learning-graph
ms.topic: include
---

Create a new Azure Active Directory application registration by following these steps:

1. In the web browser, go to the [Azure Active Directory admin center (https://aad.portal.azure.com)](https://aad.portal.azure.com) and sign-in using your Microsoft 365 developer account.
1. On the menu, select **Azure Active Directory**.

    :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-select-in-menu.png" alt-text="Screenshot showing Microsoft Azure portal Azure Active Directory." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-select-in-menu.png":::

1. Select **App registrations** from the menu.
1. Create a new app registration by selecting **New registration** in the toolbar.

    :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-registration.png" alt-text="Screenshot showing selecting an app registration in Azure Active Directory." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-registration.png":::

1. On the **Register an application** screen, enter the following values:

   - **Name**: enter a name for your application.
   - **Supported account types**: select **Accounts in any organizational directory (Any Azure AD directory - Multitenant)**.
   - **Redirect URI (optional)**: select **Web** and enter `https://localhost:5001`.
   - Select **Register**.

       :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-web-app-registration.png" alt-text="Screenshot showing how to register a web app in Azure Active Directory." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-web-app-registration.png":::

1. Once the app is created, copy the **Application (client) ID** value and save it. You'll need the value later. This value can be found on the **Overview** screen.

    :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-overview.png" alt-text="Screenshot showing the app overview information." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-overview.png":::

1. Select **Authentication** under **Manage**.

    :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-authentication-menu.png" alt-text="Screenshot showing how to select the Authentication option." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-authentication-menu.png":::

1. On the app's **Authentication** screen, enter the following values:

    - **Web / Redirect URIs**: select **Add URI** and enter a value of `https://localhost:5001/signin-oidc`.
    - **Front-channel logout URL**: enter `https://localhost:5001/signout-oidc`.
    - **Implicit grant and hybrid flows**: select **ID tokens**.
    - Select **Save** on the toolbar.

        :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-registration-authentication.png" alt-text="Screenshot showing how to redirect URIs and select ID tokens." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-app-registration-authentication.png":::

1. **Select Certificates & secrets** under **Manage**.
1. Select **New client secret**. Enter a value of **App Client Secret** in the **Description** and select any of the options for **Expires**. Select **Add** to create the secret.

    :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-client-secret.png" alt-text="Screenshot showing how to create a client secret." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-client-secret.png":::

1. Copy the client secret **Value** before you leave this page. You'll need it later.

    :::image type="content" source="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-copy-client-secret.png" alt-text="Screenshot showing how to copy the client secret." lightbox="../media/exercise-register-m365-dotnet-core-azure-ad-application/azure-ad-copy-client-secret.png":::
