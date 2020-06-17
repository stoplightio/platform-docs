# Migrating from NEXT (next.stoplight.io)

## Introduction

One of the main goals for this new version of the Stoplight Platform has been to make it easier for you to integrate Stoplight into your existing workflows. In NEXT, we were locked into a single VCS provider, GitLab. Under the hood, every NEXT project is connected to a Stoplight hosted GitLab repository.

So, the biggest difference between NEXT and the new Stoplight Platform is now you have control over which VCS provider your projects are stored in, making it easier for non-Stoplight users to contribute while continuing to use whatever tools they're comfortable with.

## When can I migrate?

If any of the following features are critical to your workflow, we suggest you wait to migrate until we've finished building a solution that fits your needs. You can request to be notified and even make suggestions by voting for features on our [public roadmap](https://meta.stoplight.io/roadmap).

|                                     |  Timeline   | Description                                                                        |
| ----------------------------------- | :---------: | ---------------------------------------------------------------------------------- |
| Docs: Theming                       |  Immediate  | Customize the theme colors for your Workspace's sidebar                            |
| Docs: Versioning                    |  Immediate  | Show/hide specific branches in each project's docs                                 |
| Docs: Table of contents ordering    | Short-term  | Customize the ordering of items in the sidebar                                     |
| Docs: Custom CSS, JS, and HTML      | Short-term  | Rich component library for composing custom API docs                               |
| Design: Shared parameters/responses |  Mid-term   | Form based editing for OpenAPI shared components                                   |
| Design: Lifecycle tags              |  Mid-term   | Add tags to build workflows around the API lifecycle                               |
| Docs: TryIt auth token generation   |  Mid-term   | Generate OAuth 1 & 2 tokens for HTTP requests in TryIt                             |
| Discussions                         |  Mid-term   | Create and resolve discussions on API designs and docs                             |
| Docs: Custom variables              | Considering | Allow users to set variable once and have it used everywhere                       |
| Docs: Redirects                     | Considering | Automatic redirects when docs routes are changed                                   |
| Docs: Integrations                  | Considering | First class support for integrations like Google analytics, Segment, Intercom, etc |
| Design: CRUD Builder                | Considering | Automatically generate a list of CRUD endpoints for a schema                       |

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

**How do I create an organization?**

In Next, you were a member of an organization where you created projects and invited team members. In the new Stoplight Platform, we've renamed organizations to "workspaces", but the concept is still the same. In your workspace, you invite team members and connect to your VCS provider (Github, Gitlab, Bitbucket, etc) to add projects.

**How do the members roles compare to the ones in NEXT?**

The roles and permissions work similar to NEXT, but some of the role names have changed. The main difference in Platform is members who need to edit projects will need to be granted access within your VCS.

| NEXT        | Platform |                                   |
| ----------- | -------- | --------------------------------- |
| Owner       | Owner    | Can change workspace settings     |
| Admin       | Admin    | Can manage members                |
| Contributor | Maker    | Can add projects                  |
| Reader      | Viewer   | Can view projects                 |
|             | Guest    | Can be granted access to projects |

**How do I publish a documentation Hub?**

In Platform, your Workspace is your documentation Hub. Workspaces are publicly accessible, but you can control access to view projects by configuring a project's visibility settings. You can also grant members and guests explicit access to view private or internal projects.

Once your projects have been added to Stoplight, there are two ways you can make sure your documentation is always up to date. You can install git webhooks to notify Stoplight whenever a change is made or you can use the Stoplight CLI to push changes.

_TODO: Add a link_

**How do I add a custom domain?**

_TODO: Add custom domain to Workspace. Considering project custom domains?_

_TODO: Add a link_

**How do I configure authentication such as Auth0 or SAML?**

_TODO: Configure Auth0 as an IdP: https://auth0.com/docs/protocols/saml/saml-configuration/design-considerations#considerations-for-using-auth0-as-identity-provider_

_TODO: Link to docs on configuring SAML_

**How do I create a new version/release of my project?**

_TODO: Git branches_

**How do I configure a Prism mock server?**

Every OpenAPI file in your Workspace has a mock server configured automatically. All you need to do is send requests to the API's unique mock URL.

_TODO: Add a link_
