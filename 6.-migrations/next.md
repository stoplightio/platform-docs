# Migrating from NEXT

## Introduction

The new Stoplight Platform is the third generation of our product, and fundamentally reimagines how Stoplight integrates into your development workflow.

When we began developing the new platform, our primary goal was to make it as easy as possible to integrate Stoplight into your existing workflows. Stoplight should enrich - not replace - these workflows, thus reducing the friction involved with rolling out a modern API development strategy at your company.

To that end, the new Stoplight Platform was built to act as a layer on top of the version control system(s) at your company - GitHub, GitLab, Bitbucket, etc. In NEXT, your API designs and docs are stored in Stoplight. In the new Stoplight Platform, these assets are stored in your own version control system.

This shift leads to a number of benefits:

1. **No lock-in:** Your data is your own, stored in your Git repositories.
2. **Tooling flexibility:** Convincing developers to adopt a new tool can be difficult. With our new approach, developers can continue to use the tools that they're most comfortable with - all they need to do is commit design/docs files to your Git repos. If some of them prefer to write OpenAPI by hand in VS Code rather than using Stoplight Studio, no problem!
3. **Workflow flexibility:** Since Stoplight is built on your VCS, it's easy to leverage the development workflows that already exist at your company - PR reviews, CI, GitHub actions, custom VCS integrations, you name it.
4. **Co locate alongside implementation:** In NEXT you are forced to store your design/docs files in a flat list, separate from the implementation they are meant to describe. In our new Platform you can organize your files however you like, including managing them in the same repo as the actual API implementation! This has a number of benefits, such as reviewing changes to design and implementation in a single Pull Request.

The list above describes some of the large fundamental opportunities our new approach opens up. Beyond that there are of course dozens of new features and enhancements packed into the new Platform.

## When can I migrate?

While the new Stoplight Platform includes a lot of new functionality, there are some features from NEXT that have not yet made their way over. We are taking this opportunity to re-imagine and improve the functionality listed below, and will be rolling it out through the rest of the year. If any of the features below are critical to your workflow, we suggest that you wait to migrate until the relevant features are released. You can continue to use Stoplight NEXT without distruption until then.

Each feature is linked to a card on our public roadmap, and we encourage you to follow the features relevant to you - we'll notify you as each is released.

|                                                                                                       |  Timeline   | Description                                                                                                                               |
| ----------------------------------------------------------------------------------------------------- | :---------: | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [Docs: Theming](https://roadmap.stoplight.io/c/52-theming-and-branding)                               |  Immediate  | Customize the branding and colors                                                                                                         |
| [Docs: Versioning](https://roadmap.stoplight.io/c/60-multiple-branches)                               |  Immediate  | Show/hide specific branches in each project's docs                                                                                        |
| [Docs: Table of contents ordering](https://roadmap.stoplight.io/c/59-customize-docs-sidebar-ordering) | Short-term  | Completely custom ordering of your docs sidebar. By default, files will be organized alphabetically, matching the order in the filesystem |
| [Docs: Custom CSS, JS, and HTML](https://roadmap.stoplight.io/c/57-embeddable-component-library)      | Short-term  | Rich component library for creating custom API docs site                                                                                  |
| [Design: Shared parameters/responses](https://roadmap.stoplight.io/c/10-openapi-shared-components)    |  Mid-term   | Form based editing for OpenAPI shared components                                                                                          |
| [Design: Lifecycle tags](https://roadmap.stoplight.io/c/65-lifecycle-tags)                            |  Mid-term   | Add tags to build workflows around your API lifecycle                                                                                     |
| [Docs: Try It OAuth token generation](https://roadmap.stoplight.io/c/58-request-maker-authentication) |  Mid-term   | Generate OAuth 1 & 2 tokens for HTTP requests in Try It                                                                                   |
| [Discussions](https://roadmap.stoplight.io/c/61-discussions-comments)                                 |  Mid-term   | Create and resolve discussions on API designs and docs                                                                                    |
| [Docs: Custom variables](https://roadmap.stoplight.io/c/47-custom-variables)                          | Considering | Allow users to set a variable once and have it used everywhere                                                                            |
| [Docs: Redirects](https://roadmap.stoplight.io/c/68-redirects)                                        | Considering | Automatic redirects when docs routes are changed                                                                                          |
| [Docs: Integrations](https://roadmap.stoplight.io/c/64-analytics-integrations)                        | Considering | First class support for integrations like Google analytics, Segment, Intercom, etc                                                        |
| [Design: CRUD Builder](https://roadmap.stoplight.io/c/63-crud-builder)                                | Considering | Automatically generate a list of CRUD endpoints for a schema                                                                              |

## How do I migrate?

> If you feel comfortable and ready to migrate, please follow the steps below. If you have any questions concerns, please don't hesitate to [reach out](mailto:support@stoplight.io) and we will schedule time to assist you. We understand that this not a trivial migration, and are here to help!
>
> Also keep in mind that you can of course copy API design files from NEXT into your existing Git repositories. This approach makes sense if you want to start managing these design assets in the same Git repos that store the code. If you are wondering which approach is best for you, please get in touch and we'll schedule some time to help you decide.

Because we've updated our approach to where your data is stored and managed (your VCS rather than our homegrown backend), this migration is a bit more involved. The goal of this migration is to move your data from Stoplight NEXT to Git repos in your VCS, and then to connect those Git repos to your new Stoplight Workspace.

### Migrating project contents

First, let's move the contents of your NEXT project into your own VCS provider.

1. Choose which NEXT project you want to migrate.
2. Follow [this guide](https://docs.stoplight.io/platform/projects/git-repo#how-to-clone-your-stoplight-git-repository) to git clone the project's contents to a folder on your computer.
3. Create a new git repository in your VCS provider ([Github](https://help.github.com/en/github/getting-started-with-github/create-a-repo), [Gitlab](https://docs.gitlab.com/ee/gitlab-basics/create-project.html), [Bitbucket](https://confluence.atlassian.com/bitbucket/create-a-git-repository-759857290.html), etc).
4. Push the project contents from your computer into your new git repository. In your terminal, while in the root of your project folder, run the following commands to push the files and history into your new Git repository.

```bash
git remote rename origin upstream

# make sure to update the URL here with the http url to the Git repo you created in step 3!
git remote add origin https://github.com/{organization}/{url}.git

git push -u origin $(git rev-parse --abbrev-ref HEAD)
```

5. Once step 4 is complete, you should see the contents of your project in your new Git repository in your VCS. Repeat these steps for each of the NEXT projects you want to migrate.

Now, let's create a Stoplight Workspace and add your projects.

5. [Create](https://stoplight.io/welcome/create) your new [Stoplight Workspace](../2.-workspaces/a.creating-a-workspace.md).
6. Please follow this [step-by-step guide](../1.-quickstarts/add-projects-quickstart.md#connect-an-existing-git-project) to connect your VCS account and add the projects from step 4.

Finally, let's invite your team to your new Stoplight workspace. The fastest way is to [configure an email domain](../2.-workspaces/d.inviting-your-team.md#make-your-workspace-discoverable) and share a link to your workspace's signup page. Alternatively, you can also [invite members](../2.-workspaces/d.inviting-your-team.md) individually using their email.

### Migrating published docs

If you have published docs for external stakeholders (customers, the general public, etc), there are a couple of things to consider before migrating.

1. Are you using a hub file (versus publishing an OpenAPI file)? If the answer is yes, then we recommend you wait until we release our hub migration tool (short term).
2. Are you using a lot of custom CSS or custom JS? If the answer is yes, then we recommend you wait until we release our new [web components](https://roadmap.stoplight.io/c/57-embeddable-component-library), which will allow for a similar level of cutomizability.

If neither of the above are relevant to your use case, then you can probably migrate! We recommend that you [reach out](mailto:support@stoplight.io) and we will schedule some time to meet and make your migration as smooth as possible.

## FAQ

The concepts in the new Stoplight Platform should be very similar to what you're used to in NEXT. Here are some commonly asked questions to help clarify those similarities and differences. If you have any additional questions, please don't hesitate to [contact us](mailto:support@stoplight.io).

**Is a Stoplight Workspace similar to an Organization in NEXT?**

Yes, they are very similar. Just like in a NEXT organization, your Workspace is where you'll invite members, add projects, and create a billing subscription.

**How do the members roles compare to the ones in NEXT?**

The roles and permissions work similar to NEXT, but some of the role names have changed. The main difference in the new Platform is members who need to edit a git project will need to be given editing access within your VCS.

We've also added a `guest` role which allows you to invite members from outside of your company and grant them access to view specific projects.

Below is a mapping of NEXT to Platform roles:

| NEXT        | Platform |                                   |
| ----------- | -------- | --------------------------------- |
| Owner       | Owner    | Can change workspace settings     |
| Admin       | Admin    | Can manage members                |
| Contributor | Maker    | Can add projects                  |
| Reader      | Viewer   | Can view projects                 |
|             | Guest    | Can be granted access to projects |

**How do I publish my documentation as a Hub?**

In the new Platform, your Workspace is your documentation Hub. Workspaces are publicly accessible, and you control access to view projects by configuring a project's visibility settings.

For example if you want a project to only be visible by Workspace members, you can set the project's visibility to `internal`. You can also give members and guests explicit access to view specific private or internal projects.

**How do I update the contents of my project's documentation?**

When adding a project to your Stoplight Workspace, a git webhook will be installed on the VCS repository. This allows Stoplight to automatically update your documentation when any of the API design assets in the repository have changed.

The contents of the project can then be updated from any one of your favorite tools such as Stoplight Studio or even directly in the VCS provider. As long as the changes are pushed to the git repository, they will be automatically synced with your Stoplight Workspace.

<!-- **How do I add a custom domain to my documentation?** -->

<!-- **How do I configure authentication such as Auth0 or SAML?** -->

<!-- TODO: Configure Auth0 as an IdP: https://auth0.com/docs/protocols/saml/saml-configuration/design-considerations#considerations-for-using-auth0-as-identity-provider -->

<!-- TODO: Link to docs on configuring SAML -->

**How do I create a new version/release of my project?**

In NEXT, the versioning and releases feature was built on top of [git branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging). To accomplish the same in Platform, you can create a git branch in your project using Stoplight Studio or your favorite git tool.

<!-- TODO: Add a link to multi-branch support -->

**How do I configure a Prism mock server?**

Every OpenAPI file in your Workspace has a mock server configured automatically. All you need to do is send requests to the API's unique mock URL. For more information, please read this [guide on mocking in Stoplight](../3.-design/d.setting-up-a-mock-server.md).

<!-- TODO: Add a link -->
