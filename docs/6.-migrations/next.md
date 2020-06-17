# Migrating from NEXT (next.stoplight.io)

## Introduction

One of the main goals for this new version of the Stoplight Platform has been to make it easier for you to integrate Stoplight into your existing workflows. In NEXT, we were locked into a single VCS provider, GitLab. Under the hood, every NEXT project is connected to a Stoplight hosted GitLab repository.

The biggest difference between NEXT and the new Stoplight Platform is now you have control over what VCS provider your projects are stored in. This allows you to keep your source of truth in one location, making it easier for non-Stoplight users to contribute while continuing to use the tools they're comfortable with.

## When can I migrate?

If any of the following features are critical to your workflow, we suggest you wait to migrate until we've finished building a solution that fits your needs. You can request to be notified and even make suggestions by voting for features on our [public roadmap](https://meta.stoplight.io/roadmap).

<!-- TODO: Add productboard links for each feature -->

|                                     |  Timeline   | Description                                                                                                                               |
| ----------------------------------- | :---------: | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Docs: Theming                       |  Immediate  | Customize the theme colors for your Workspace's sidebar                                                                                   |
| Docs: Versioning                    |  Immediate  | Show/hide specific branches in each project's docs                                                                                        |
| Docs: Table of contents ordering    | Short-term  | Completely custom ordering of your docs sidebar. By default, files will be organized alphabetically, matching the order in the filesystem |
| Docs: Custom CSS, JS, and HTML      | Short-term  | Rich component library for composing custom API docs                                                                                      |
| Design: Shared parameters/responses |  Mid-term   | Form based editing for OpenAPI shared components                                                                                          |
| Design: Lifecycle tags              |  Mid-term   | Add tags to build workflows around the API lifecycle                                                                                      |
| Docs: TryIt auth token generation   |  Mid-term   | Generate OAuth 1 & 2 tokens for HTTP requests in TryIt                                                                                    |
| Discussions                         |  Mid-term   | Create and resolve discussions on API designs and docs                                                                                    |
| Docs: Custom variables              | Considering | Allow users to set variable once and have it used everywhere                                                                              |
| Docs: Redirects                     | Considering | Automatic redirects when docs routes are changed                                                                                          |
| Docs: Integrations                  | Considering | First class support for integrations like Google analytics, Segment, Intercom, etc                                                        |
| Design: CRUD Builder                | Considering | Automatically generate a list of CRUD endpoints for a schema                                                                              |

## How do I migrate?

> If you feel comfortable and ready to migrate, please follow the steps below. If you have any questions concerns, please don't hesistate to [reach out](mailto:support@stoplight.io) and we will schedule time to assist you.

The goal of this migration is to move your projects from Stoplight NEXT to your new Stoplight Workspace.

First, let's move the contents of your NEXT project into your own VCS provider.

1. Choose which NEXT project you want to migrate.
2. Follow [this guide](https://docs.stoplight.io/platform/projects/git-repo) to git clone the project's contents to a folder on your computer.
3. Create a new git repository in your VCS provider ([Github](https://help.github.com/en/github/getting-started-with-github/create-a-repo), [Gitlab](https://docs.gitlab.com/ee/gitlab-basics/create-project.html), [Bitbucket](https://confluence.atlassian.com/bitbucket/create-a-git-repository-759857290.html), etc).
4. Push the project contents from your computer into your new git repository.

```bash
git remote rename origin upstream
git remote add origin https://github.com/{organization}/{url}.git
git push -u origin $(git rev-parse --abbrev-ref HEAD)
```

5. Repeat these steps for each of the NEXT projects you want to migrate.

Now, let's create a Stoplight Workspace and add your projects.

5. [Create](https://stoplight.io/welcome/create) your new [Stoplight Workspace](./a.creating-a-workspace.md).
6. Please follow this [step-by-step guide](../1.-quickstarts/add-projects-quickstart.md#connect-an-existing-git-project) to connect your VCS account and add the projects from step 4.

Finally, let's invite your team. The fastest way is to [configure an email domain](../2.-workspaces/d.inviting-your-team.md#make-your-workspace-discoverable) and share a link to your workspace's signup page. Or you can also [invite members](../2.-workspaces/d.inviting-your-team.md) individually using their email.

## FAQ

The concepts in the new Stoplight Platform should be very similar to what you're used to in NEXT. Here are some commonly asked questions to help clarify those similarities and differences. If you have any additional questions, please don't hesistate to [contact us](mailto:support@stoplight.io).

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

Every OpenAPI file in your Workspace has a mock server configured automatically. All you need to do is send requests to the API's unique mock URL. For more information, please read this [guide on mocking in Stoplight](./d.setting-up-a-mock-server.md).

<!-- TODO: Add a link -->
