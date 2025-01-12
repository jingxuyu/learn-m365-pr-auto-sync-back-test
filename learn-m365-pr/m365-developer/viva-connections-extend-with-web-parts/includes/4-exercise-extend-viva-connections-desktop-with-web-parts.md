In this exercise, you'll build a SharePoint Framework web part that gets data from a SharePoint list. You'll then add the web part to Viva Connections desktop.

## Create a new solution

To start, create a solution by using the SharePoint Framework Yeoman generator:

1. Create a folder for your project named *spfx-company-announcements-webpart*.
1. In a terminal, change the working directory to *spfx-company-announcements-webpart*.
1. Run the `yo @microsoft/sharepoint` command to start scaffolding a new solution.
1. Answer the generator's prompts:

   | Prompt | Entry |
   | --------- | ----------- |
   | What is your solution name? | **spfx-company-announcements-webpart** |
   | Only SharePoint Online (latest) is supported. For earlier versions of SharePoint (2016 and 2019) please use the 1.12.1 version of the generator. | **SharePoint Online only (latest)** |
   | Where do you want to place the files? | **Use the current folder** |
   | Do you want to allow the tenant admin the choice of being able to deploy the solution to all sites immediately without running any feature deployment or adding apps in sites? | **No** |
   | Will the components in the solution require permissions to access web APIs that are unique and not shared with other components in the tenant? | **No** |
   | Which type of client-side component to create? | **WebPart** |
   | What is your Web part name? | **Company announcements** |
   | What is your Web part description? | **Shows company announcements** |
   | Which framework would you like to use? | **No JavaScript framework** |
   
1. Wait for the project creation to finish. It might take a few minutes.
   
   > [!TIP]
   > While you're waiting, you'll likely see some warnings. You can safely ignore them.

## Install the development certificate

The SharePoint Framework uses a workbench hosted in SharePoint Online where you can test your code before deploying it to Viva Connections. When you test your code, you start a local web server by using Gulp. The SharePoint Framework workbench then loads files from your local server so you can test them. 

To let the workbench load files from your local development server, use the following procedure to trust the development certificate from the SharePoint Framework.

> [!IMPORTANT]
> Install the development certificate only once on your machine. When you create a new project, the SharePoint Framework will use the previously installed certificate. If you've done this already, you can skip these steps.

1. Open a terminal.
1. Change the working directory to your project folder.
1. Run the `gulp trust-dev-cert` command.
1. Follow the instructions on the screen to complete the installation of the certificate.

## Edit the web part

After you create the project, the next step is to extend the web part so that it loads company announcements from the list and shows them on the page:

1. Open the project in your code editor.
1. In the code editor, open the *./src/webparts/companyAnnouncements/CompanyAnnouncementsWebPart.ts* file.
1. In the top section of the file, add `import { SPHttpClient } from '@microsoft/sp-http';`.
1. Clear the contents of the `render` method.
1. In the `render` method, add the following code block:

   ```typescript
   this.context.spHttpClient
     .get(`${this.context.pageContext.web.absoluteUrl}/_api/web/lists/getByTitle('Announcements')/items?$select=Title,Description,Important`,
       SPHttpClient.configurations.v1,
       {
         headers: {
           'accept': 'application/json;odata.metadata=none'
         }
       })
     .then(response => response.json())
     .then(announcements => {
       // todo: display results
     })
     .catch(error => this.context.statusRenderer.renderError(this.domElement, error));
   ```

   You use `spHttpClient` to retrieve the list of announcements from the previously created **Announcements** list. `spHttpClient` wraps the standard `fetch` API and is authenticated to call SharePoint APIs.
   
   In the API URL, you use the OData `$select` parameter to specify the list of properties to retrieve. These properties match the columns from the **Announcements** list. 
   
   While calling the SharePoint API, you also set the `accept` header to suppress metadata in the response. It allows you to minimize the amount of data sent over the network.
   
   After you receive the response from the API, you retrieve its JSON response. If an error occurs while you're calling the API, it will appear in the web part's content area through the helper method exposed by the web part.

1. After you retrieve announcements from the list, the next step is to display them in the web part. In the last `then` clause, replace the `// todo: display results` comment with the following block:

   ```typescript
   const announcementsHtml = announcements.value.map(announcement =>
     `<dt${announcement.Important ?
       ` class="${styles.important}"` : ''}>${announcement.Title}</dt>
     <dd>${announcement.Description}</dd>`);
   
   this.domElement.innerHTML = `
   <div class="${styles.companyAnnouncements}">
     <div class="${styles.container}">
       <div class="${styles.title}">Announcements</div>
       <dl>
         ${announcementsHtml.join('')}
       </dl>
     </div>
   </div>
   `;
   ```

   The `announcement` variable contains the `value` property that holds an array of announcements from the list. For each announcement, you create an HTML string with the `dt` and `dd` elements holding the announcement's contents. Next, you combine the announcements into a single HTML string and display it in the web part's DOM element.

   > [!TIP]
   > When possible, you should always use semantic HTML rather than the generic `div` and `span` elements. Using semantic HTML, like a heading (`h1`-`h6`) or a definition list (`dl`), helps people who use screen readers and other accessibility tools to follow the page's contents more easily.

1. To save your changes, select **File** > **Save** or select Ctrl+S on the keyboard (CMD+S on macOS).

## Style the web part's contents

To show announcements in the web part, you used the standard `dl`, `dt`, and `dd` HTML elements. You also included a custom CSS class named `important` to highlight important announcements. Now add CSS styles to format how announcements and important announcements are displayed:

1. In the code editor, open the *./src/webparts/companyAnnouncements/CompanyAnnouncementsWebPart.module.scss* file.
1. Replace the contents of the file with the following code:

   ```css
   @import '~@microsoft/sp-office-ui-fabric-core/dist/sass/SPFabricCore.scss';
   
   .companyAnnouncements {
     .container {
       @include ms-Grid;
       color: var(--primaryText, #323130);
     }
   
     .title {
       @include ms-fontSize-18;
       @include ms-fontWeight-semibold;
     }
   
     dt {
       @include ms-fontWeight-bold;
       @include ms-fontSize-14;
       margin-top: 1rem;
   
       &.important {
         color: $ms-color-red;
       }
     }
   
     dd {
       margin-left: 0;
     }
   }
   ```

   You start with importing Fluent UI to ensure consistent styling with Microsoft 365. Next, you add a CSS class for the web part's title. In the class, you refer to the font definitions from Fluent UI. Then, you define styling for the `dt` and `dd` elements that you used to display announcements. 
   
   Like you did for the web part's title, you refer to Fluent UI styles to ensure consistency. To highlight important announcements, you define an extra class named `important`, which uses red text as defined in Fluent UI.

1. To save your changes, select **File** > **Save** or select Ctrl+S on the keyboard (CMD+S on macOS).

## Test the web part

To build and preview the web part for company announcements:

1. In a terminal, run the `gulp serve --nobrowser` command. This command will start a local web server on `https://localhost:4321`.

   :::image type="content" source="../media/4-terminal-serve.png" alt-text="Screenshot of a terminal window with the output of the gulp serve command.":::

   > [!WARNING]
   > If you see the following warning in the terminal, it means that the local web server couldn't load your development certificate:
   >
   > :::image type="content" source="../media/4-terminal-serve-warning.png" alt-text="Screenshot of a terminal window that shows a warning after running the gulp serve command.":::
   >
   > _Warning - [spfx-serve] When serving in HTTPS mode, a PFX cert path or a cert path and a key path must be provided, or a dev certificate must be generated and trusted. If a SSL certificate isn't provided, a default, self-signed certificate will be used. Expect browser security warnings._
   >
   > To fix this problem, stop the web server by selecting Ctrl+C and run the `gulp trust-dev-cert` command.
1. In a web browser, go to the workbench at `<Home site url>/_layouts/workbench.aspx`. The home site URL is where you created the **Announcements** list in the previous exercise.
   
   > [!WARNING]
   > After you open the workbench, if you see the following error, it means that the local web server couldn't load your development certificate:
   >
   > :::image type="content" source="../media/4-workbench-warning.png" alt-text="Screenshot of the SharePoint workbench that shows a warning message about being unable to load the local manifest.":::
   >
   > _Your web part will not appear in the toolbox. Please make sure “gulp serve” is running in a web part project. Please refresh the page once “gulp serve” is running._
   >
   > To fix this problem, stop the web server by selecting Ctrl+C and run the `gulp trust-dev-cert` command.
1. To add the newly created web part to the canvas, select the **+** (plus) button to open the toolbox.

   :::image type="content" source="../media/4-open-toolbox.png" alt-text="Screenshot of the plus button to open the toolbox in the SharePoint workbench.":::

1. On the search bar, type **Company announcements** and select the web part.

   :::image type="content" source="../media/4-toolbox-company-announcements-web-part.png" alt-text="Screenshot of the web part for company announcements in the toolbox.":::
   
   If you followed all steps successfully, you'll see your announcements from the **Announcements** list displayed in the workbench.
   
   :::image type="content" source="../media/4-company-announcements-web-part.png" alt-text="Screenshot that shows the web part for company announcements displaying announcements in the SharePoint workbench.":::
   
   The titles of announcements selected as important appear in red.

1. To stop the development web server, go back to the terminal and select Ctrl+C.

## Deploy the web part to Viva Connections

You've built the **Company announcements** web part by using the SharePoint Framework. Now you can deploy it to Viva Connections.

To package the web part into an app by using Gulp:

1. Go to the terminal where the working directory is the root folder of the project.
1. To build the solution in release mode, run the `gulp bundle --ship` command.
1. To make a release mode package of the solution, run the `gulp package-solution --ship` command.
 
The `package-solution` task creates an app package file named *spfx-company-announcements-webpart.sppkg* in the *./sharepoint/solution* folder. This file is your app package. Next, you'll deploy this package into the SharePoint app catalog, which contains all Viva Connections extensions.

If you don't have an app catalog in your tenant, create it now:

1. In a web browser, go to the [Microsoft 365 admin center](https://admin.microsoft.com).
1. From the side menu, select **Show all**.
1. From the **Admin centers** list, select **SharePoint**.
1. In the SharePoint admin center, from the side menu, select **More features**.
1. From the **Apps** section, select the **Open** button to go to the **Apps** admin page.
1. Under **Apps**, select **App Catalog**.
1. If the site opens, you already have an app catalog and you can skip further steps.

   If the app catalog doesn't exist, you're prompted to create one.

1. From the list of options, select **Automatically create a new app catalog site**, and then select **OK**.

Deploy your application to the catalog:

1. In a web browser, go to the SharePoint app catalog.
1. From the side menu in the catalog, select **Apps for SharePoint**.
1. Drag the *spfx-company-announcements-webpart.sppkg* file into the list.
1. SharePoint asks you to confirm and deploy the package. Select **Deploy** to make the package available to install on SharePoint sites.

   :::image type="content" source="../media/4-sharepoint-app-catalog-prompt.png" alt-text="Screenshot of the SharePoint app catalog prompt to confirm deploying the uploaded solution package.":::

After the app is successfully deployed in the app catalog, you need to install it on your home site:

1. In a web browser, go to the home site.
1. From the top menu, select the **Settings** (gear) icon.
1. From the **SharePoint** section, select the **Add an app** link. 
1. In the search box on the **My Apps** page, type **Company** and find the **spfx-company-announcements-webpart-client-side-solution** app.
1. Select the **Add** button.

You can now add the **Company announcements** web part onto any SharePoint page on the site. To add the web part on the home page of the home site:

1. In a web browser, go to the home site.
1. To ensure that you're on the home page, select **Home** from the top menu.
1. To edit the page, select **Edit** from the page menu.
1. Choose an area inside the page where you'll place the web part.
1. Select the **+** button to open the toolbox.
1. Search for the **Company announcements** web part.
1. Select the web part to add it to the page.
1. From the page menu, select **Republish**.

The **Company announcements** web part is now on the home page of your home site. Test the app to see how this web part looks in Viva Connections in Microsoft Teams:

1. Open the Microsoft Teams desktop client, or go to the [Teams site](https://teams.microsoft.com) in a web browser.
1. Open the Viva connection app and confirm that the **Company announcements** web part displays all announcements on the home site's home page.

   :::image type="content" source="../media/4-company-announcements-web-part-viva-connections-desktop.png" alt-text="Screenshot that shows the web part for company announcements displaying announcements in Viva Connections desktop.":::
