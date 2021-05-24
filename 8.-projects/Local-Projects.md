# Working with Local Projects

Stoplight works vis-a-vis with Git to integrate seamlessly with your current development and collaboration workflows. In case you do not make use of Git, or use a version control not supported by Stoplight, you can still make use of the platform. 

## **What are Local Projects?**

**Local projects** on Stoplight are the ones not associated with a Git repo. This means you would have to store the content of those projects on your own local or cloud storage. 

Oneway to work on local projects is through the **web app**, but any changes you make, are only limited to your current web session and your progress will be lost once you lose session data. 

The other way is to make use of **Studio (desktop app)** and **Stoplight CLI.** 

On the **desktop app**, you can import and edit projects same as the web app, and can save your changes on your private storage. 

Through the **CLI**, a command-line tool, available as an NPM module, you can push these changes to your workspace, and have them show up on **Explorer** and shared externally as documentation, just like any other project. 

## **Adding Local Projects**

Adding local projects to your workspace is very easy. 

1. From your **Dashboard,** click the **+** ( add project) button next to your workspace name. 
2. On the **Add Projects** page, select add **via Stoplight CLI.**
3. Enter the project **name**, and click **Add Project**. 

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fa434d62-8951-4834-8fb3-3c355be81990/Screen_Shot_2021-02-26_at_5.44.55_PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fa434d62-8951-4834-8fb3-3c355be81990/Screen_Shot_2021-02-26_at_5.44.55_PM.png)

4. This is going to create an empty project where you can push data. Copy the **command** on the screen.

5. Open your terminal, navigate to the root folder of the project and **run this command**. This will push data to your workspace. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/13b7a5ac-d196-4d91-b1bb-94946dc004bd/Screen_Shot_2021-02-16_at_1.44.36_AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/13b7a5ac-d196-4d91-b1bb-94946dc004bd/Screen_Shot_2021-02-16_at_1.44.36_AM.png)

## **Editing Local Files**

To edit local files, you need to download the Studio desktop app. Start by:

1. Downloading Studio Desktop from [here](https://stoplight.io/studio/).
2. Open the project in Studio Desktop and edit using the form or code editors. Read the [Studio documentation](https://meta.stoplight.io/docs/studio/) for more specifics.

After you are done making changes, run the above CLI command again, and your content will be pushed to your workspace, or automate publishing in [continuous integration](https://meta.stoplight.io/docs/platform/2.-workspaces/g.automating-publishing.md#continous-integration).

## Whats Next?

Once done editing, you can push the files using the CLI, or automate publishing in continuous integration. Read on to find out how: 

- **Using Stoplight CLI**
- **Continuous Integration**