---
tags: [Workspaces]
---

# Add Projects

Within Workspaces, the most important concept in Stoplight is "Projects". Projects are a place for you to manage APIs, articles, and any other files that you want to store together.

## What is a Project

Projects in Stoplight are usually associated with a Git repository, which can contain anything you would expect to find in a repository: source code, API descriptions, images, Markdown articles, maybe some Excel spreadsheets. Stoplight will analyze the contents of a project looking for files it knows how to analyze, and ignore the rest.

Stoplight looks for: 

- API Description Documents in OpenAPI v2, OpenAPI v3, and JSON Schema.
- Markdown articles
- Images

Different types of projects will contain different combinations. Here are a few possible ways projects might be used:

1. **An open-source library:** JavaScript code and Markdown articles.
2. **A REST API:** PHP source code, API Descriptions written in OpenAPI, and Markdown for "How To" instructions.
3. **Community Contributed Documentation:** Markdown articles, but source code is hidden in another repository.

When designing an API, you can start with the API descriptions before the API even exists, then add the source code later, and any changes to the API can be made in the same pull request as the changes to the code. 

## Add Projects from Git

The quickest and recommended way to get projects into Stoplight is to pull them in from Git. 

1. Log in to your workspace and navigate to **Explorer**.
2. Click on **Add projects from your Git Provider**.
>If you cannot connect your Git provider, you can use the [Stoplight CLI](#projects-without-git) instead.
1.  Click on the Git provider of your choice. 
> If your git provider isn't listed or you're using a custom configuration, lets get you set up [here](#custom-configuration-for-git). 
4. Click on **Connect with *Your Git Provider***. Follow the instructions on the popup screen to authenticate.
5. Upon successful authentication, you should see your organizations listed. Choose the organization and select the repositories you want to import. Next, click **Add Projects**.

![add-projects](../assets/images/git-connect-compressed.gif)

If the repository has Markdown articles and/or API descriptions, then you will see them show up once the analyzer is finished running. 

Alternatively, you can start from scratch.

## Brand New Projects

Using [Stoplight Studio](../3.-design/a.overview.md), you can create and edit the contents of your projects and push changes back to the Git repository when you're done. 

## Projects without Git

Git is very popular, but not used by everyone. If a different version control system is in use like Mercurial, SVN, SourceSafe, Bazaar, or your team uses another way to keep all their work organized, Stoplight has you covered.

Stoplight CLI is a command-line tool, built as an NPM module, which can publish changes to Stoplight, and have them show up in Explorer just like any other project. They won't be editable in Studio, but the content will be available to read and search like anything else. 

1. Navigate to the **Add Projects** section and click on **Add project manually**.
2. Give this project a name, and click **Add Project**. This is going to create an empty project where you can then push data. 
3. **Copy the command** on the screen. Next, navigate to the root folder of the project and **run this command**. This should push data to this project, and you can view it in Explorer. 

Read more about [working with local projects](f.working-with-local-projects.md).

You can add this command to your Continuous Integration server to update the contents whenever something changes.

## Custom configuration for Git

1. Click on **Add Integrations** in the **Add projects from your Git Provider** section or the **Integrations** section in your workspace settings. 
2. Click **Configure** in front of the Git provider you're looking to set up a custom configuration for. 
3. Select **Customize integration settings** and add your desired configuration. Test it out by clicking `Test Settings`. Press `Save`. You're good to go! Happy [adding projects](#add-projects-from-Git-Provider).

Read more about [configuring Git](configure-git/a.configuring-git.md).

If you didn't find a Git provider of your choice or your project isn't on Git, follow the instructions in **Projects without Git** section. 

## Organize Projects

Who controls what projects, how many APIs go in a repo, etc. are all decisions that need to be made within your organization. Stoplight has no bias towards a "monorepo" or a "multirepo" approach, it supports either. 

If you are using a "monorepo" approach, you might have one project, with a directory for each API, and contain the source code and API description inside that directory.

If you are using a "multirepo" approach, you might have one project for each API, and contain the source code and API description inside each project in any directory structure you like.

Next, lets learn about [configuring projects](c.config.md). 
