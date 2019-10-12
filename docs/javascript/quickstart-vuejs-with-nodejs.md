---
title: "Quickstart: Create your first Vue.js app"
description: In this quickstart, you create a Vue.js app in Visual Studio using the Node.js Tools for Visual Studio
ms.custom: "seodec18"
ms.date: 09/24/2018
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: "mikejo5000"
ms.author: "mikejo"
manager: jillfra
dev_langs:
  - JavaScript
ms.workload:
  - "nodejs"
---
# Quickstart: Use Visual Studio to create your first Vue.js app

In this 5-10 minute introduction to the Visual Studio integrated development environment (IDE), you'll create and run a simple Vue.js web application.

> [!IMPORTANT]
> This article requires the Vue.js template, which is available starting in Visual Studio 2017 version 15.8.

## Prerequisites

* You must have Visual Studio installed and the Node.js development workload.

    ::: moniker range=">=vs-2019"
    If you haven't already installed Visual Studio 2019, go to the [Visual Studio downloads](https://visualstudio.microsoft.com/downloads/) page to install it for free.
    ::: moniker-end
    ::: moniker range="vs-2017"
    If you haven't already installed Visual Studio 2017, go to the [Visual Studio downloads](https://visualstudio.microsoft.com/downloads/) page to install it for free.
    ::: moniker-end

    If you need to install the workload but already have Visual Studio, go to **Tools** > **Get Tools and Features...**, which opens the Visual Studio Installer. Choose the **Node.js development** workload, then choose **Modify**.

    ![Node.js workload in VS Installer](../ide/media/quickstart-nodejs-workload.png)

* You must have the Node.js runtime installed.

    If you don't have it installed, install the LTS version from the [Node.js](https://nodejs.org/en/download/) website. In general, Visual Studio automatically detects the installed Node.js runtime. If it does not detect an installed runtime, you can configure your project to reference the installed runtime in the properties page (after you create a project, right-click the project node and choose **Properties**).

## Create a project

First, you'll create a Vue.js web application project.

1. If you don't have the Node.js runtime already installed, install the LTS version from the [Node.js](https://nodejs.org/en/download/) website.

    In general, Visual Studio automatically detects the installed Node.js runtime. If it doesn't detect an installed runtime, you can configure your project to reference the installed runtime in the properties page (after you create a project, right-click the project node and choose **Properties**).

1. Open Visual Studio.

1. Create a new project.

    ::: moniker range=">=vs-2019"
    Press **Esc** to close the start window. Type **Ctrl + Q** to open the search box, type **Basic Vue.js**, then choose **Basic Vue.js Web application** (either JavaScript or TypeScript). In the dialog box that appears, type the name **basic-vuejs**, and then choose **Create**.

    ![Vue.js template](../javascript/media/vs-2019/vuejs-template.png)
    ::: moniker-end
    ::: moniker range="vs-2017"
    From the top menu bar, choose **File** > **New** > **Project**. In the left pane of the **New Project** dialog box, expand **JavaScript** or **TypeScript**, then choose **Node.js**. In the middle pane, choose **Basic Vue.js Web application**, type the name **basic-vuejs**, and then choose **OK**.

    ![Vue.js template](../javascript/media/vuejs-template.png)
    ::: moniker-end
    If you don't see the **Basic Vue.js Web application** project template, you must add the **Node.js development** workload. For detailed instructions, see the [Prerequisites](#prerequisites).

    Visual Studio creates the new project. The new project opens in Solution Explorer (right pane).

1. Check the Output window (lower pane) for progress on installing the npm packages required for the application.

1. In Solution Explorer, open the **npm** node and make sure that all the listed npm packages are installed.

    If any packages are missing (exclamation point icon), you can right-click the **npm** node and choose **Install Missing npm Packages**.

## Explore the IDE

1. Take a look at **Solution Explorer** in the right pane.

     ![Vue.js solution](../javascript/media/vuejs-solution.png)

   - Highlighted in bold is your project, using the name you gave in the **New Project** dialog box. On disk, this project is represented by a .*njsproj* file in your project folder.

   - At the top level is a solution, which by default has the same name as your project. A solution, represented by a .*sln* file on disk, is a container for one or more related projects.

   - The **npm** node shows any installed npm packages. You can right-click the npm node to search for and install npm packages using a dialog box.

2. If you want to install npm packages or run Node.js commands from a command prompt, right-click the project node and choose **Open Command Prompt Here**.

## Add a .vue file to the project

1. In Solution Explorer, right-click any folder such as the *src/components* folder, and then choose **Add** > **New Item**.

1. Select either **JavaScript Vue Single File Component** or **TypeScript Vue Single File Component**, and then click **Add**.

    Visual Studio adds the new file to the project.

## Build the project

1. (TypeScript project only) From Visual Studio, choose **Build** > **Clean Solution**.

1. Next, choose **Build** > **Build Solution** to build the project. Check the **Output** window to see build results, and choose **Build** from the **Show output from** list.

    The Vue.js project template uses the `build` npm script by configuring a post build event. If you want to modify this setting, open the project file (*\<projectname\>.njsproj*) from Windows Explorer and locate this line of code:

    ```xml
    <PostBuildEvent>npm run build</PostBuildEvent>
    ```

## Run the application

1. Press **Ctrl**+**F5** (or **Debug > Start Without Debugging**) to run the application.

   In the console, you see a message *Starting Development Server*.

   Then, the app opens in a browser.

   ![Vue.js app running in the browser](../javascript/media/vuejs-running-app.png)

1. Close the web browser.

Congratulations on completing this Quickstart! We hope you learned a little bit about using the Visual Studio IDE with Vue.js. If you'd like to delve deeper into its capabilities, continue with a tutorial in the **Tutorials** section of the table of contents.

## Next steps

- Go through the [Tutorial for Node.js and Express](../nodejs/tutorial-nodejs.md)
- Go through the [Tutorial for Node.js and React](/visualstudio/javascript/tutorial-nodejs-with-react-and-jsx)
- [Deploy the app to Linux App Service](../javascript/publish-nodejs-app-azure.md)