Power Apps defines three types of apps: canvas, model-driven, and portals. This unit focuses on the steps and components required to build a Canvas app. The process to create a canvas app starts with logging into make.powerapps.com to access Power Apps Studio. Power Apps Studio is the name of the web interface used to build the app. With Power Apps, there's no client to download or install, since everything is done from the browser.

There are three ways to get started creating a canvas app:

 *  **Start from blank.** Starting from blank lets the user create a fully customizable app. With a blank canvas, the user's prompted to choose the format of the app, which is either Tablet or Phone. While both formats can be used interchangeably on a mobile device, a tablet, or a computer, each has different defaults around sizing of the screens and controls. Once you choose the format for an app, you can't change it.
 *  **Start from a template.** Start from pre-made templates and then customize as needed.
 *  **Start from data.** Start by connecting to existing data in the services or applications with which they're familiar and get a ready-made canvas app in minutes.

When creating a new app or opening an existing app, Power Apps Studio displays three panes:

 *  **Left pane.** By default you can see a visual hierarchy (Tree view) of the components on each screen of the app. Selecting the icons to the left changes the view of this pane. Selecting the database icon provides a view of Data sources, which includes available Common Data Service entities and available connectors.
 *  **Middle pane.** This pane displays the actual canvas for the application. When starting from a blank canvas, the app creator is prompted to either connect to data or enter an item from the insert tab.
 *  **Right pane.** This pane displays the properties and advanced configuration options for the selected control. Depending on the type of control selected, the properties include a field for the associated data source.

### Data sources

There are many ways to add data sources to an app. When starting with a blank canvas, the app creator can either add controls or connect to a data source.

 *  If the app creator chooses to connect to a data source, the **Data sources** view is displayed in the left pane. This view enables the user to select from available Common Data Source entities and connectors to be used by the app, even before adding controls to the canvas.
 *  If the app creator starts by adding controls, data sources can be added when configuring the properties for the individual controls.

### Controls

Controls are the user interface elements of the application, whose properties can be configured for appearance and behavior. The app creator builds the canvas app by adding controls from the **Insert** tab on the top ribbon of the screen. PowerApps has over 40 controls available to add to a canvas app. As certain types of controls are added, the app creator is prompted to select a data source.

The following controls are available to app creators:

 *  **Gallery.** The Gallery control is used to display records from a table of data. The display of a record is then defined by a template, which can be customized. This design enables the app creator to control which fields are displayed and how they're formatted. Power Apps then applies this template automatically to every record in the data. When adding a gallery, the user's prompted to select a data source.
 *  **Forms.** Forms are designed to work with a specific record. Display forms enable the app user to view detailed information for an existing record. Edit forms enable the user to create a new record and edit an existing one. When adding a form control, the app creator can connect to a data source, which opens the **Data Sources** view on the right pane of the screen.
 *  **Input controls.** To provide maximum flexibility in customizing apps, Power Apps has a large selection of Input controls. Text inputs, buttons, dropdowns, toggles, date pickers, and sliders are a few examples of the various input controls that are available. App creators can add these controls to galleries, forms, and screens to build a functional and aesthetic experience for the app. All inputs have a multitude of settings for default data, formatting, and actions, all of which enables the app creator to build an app that has the right user experience for their business. Depending on the type of input, the **Items** field that appears under **Properties** enables the app creator to select an available data source.
 *  **Media controls.** Power Apps provides a rich set of controls that enable app users to play videos and browse through channels from the Microsoft Stream service. Hardware-based controls are also available for accessing the device camera and microphone.
 *  **Charts.** Besides supporting pie charts, line charts, and column charts, Power Apps also takes advantage of existing Power BI data analysis and reporting by enabling app creators to display Power BI tiles inside their canvas apps.
 *  **Icons.** These controls include arrows, geometric shapes, action icons, and symbols which app creators can configure to interact with their app. For example, the left and right arrow can be used for navigation of the app.
 *  **Custom controls.** App creators can create custom controls to use in a single app or across apps.
 *  **AI Builder.** With AI Builder, app creators can add intelligence to their apps even if they have no coding or data science skills. Such updates can be made by automating processes and predicting outcomes. For example, the business card reader component can detect business cards and extract their information. By using AI Builder, data is identified and extracted using the properties associated with the control. Besides the business card reader, there are other AI controls that are available, including form processor, object detector, and text recognizer in preview.

App creators can also use formulas to configure controls in their canvas apps. In Power Apps, formulas can calculate values and do other tasks (as they do in Excel) and respond to user input. For example, you can build a formula that determines how the app responds when users select a button or provide other input. These formulas might display a different screen, update a data source that is external to the app, or create a table that contains a subset of the data in an existing table.

**Additional reading.** For more information, see [Add and configure a canvas-app control in Power Apps](/powerapps/maker/canvas-apps/add-configure-controls) and browse the [control reference](/powerapps/maker/canvas-apps/reference-properties) for the complete list of controls and their associated properties. See [formula reference for Power Apps](/powerapps/maker/canvas-apps/formula-reference) for the complete list of functions, operators, and other building blocks you can use.

### Testing and monitoring an app

As an app is being created, the app creator can run it in the browser and check for formula and accessibility errors, warnings, and tips by selecting the App checker icon. You can run an app by selecting the play icon or pressing F5.

Power Apps also offers more advanced tools for testing and monitoring an application.

 *  **Test Studio (experimental).** Power Apps Test Studio is a low-code solution that is used to write, organize, and automate tests for canvas apps.
 *  **Monitor (experimental).** The initial version of Monitor is focused on network activity similar to a network trace in the browser. It provides details of each network call including how long it took, how much data was returned, and if there was an error.

Saving changes to a canvas app automatically publishes them only for the app creator and anyone else who has permissions to edit the app. When an app creator finishes making changes, they must explicitly publish the changes to make them available to everyone to which the app is shared.

Once the app is published, the app creator can specify which users in the organization can run the app and which users can modify and even reshare the app. The app creator can apply these permissions by specifying each user by name or by specifying a security group in Azure Active Directory.

**Additional reading.** For more information on creating canvas apps, see [Create your first app](/powerapps/maker/canvas-apps/get-started-test-drive). This article includes links to creating a canvas app from a template, creating an app using data, and much more.

For information on creating a model-driven app, see [Build your first model-driven app from scratch](/powerapps/maker/model-driven-apps/build-first-model-driven-app).

For information on creating a starter portal, see [Create a Common Data Service starter portal](/powerapps/maker/portals/create-portal).
