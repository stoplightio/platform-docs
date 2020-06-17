# Migrating from NEXT (next.stoplight.io)

## Introduction

One of the main goals for this new version of the Stoplight Platform has been to make it easier for you to integrate Stoplight into your existing workflows. In NEXT, we were locked into a single VCS provider, GitLab. Under the hood, every NEXT project is connected to a Stoplight hosted GitLab repository.

So, the biggest difference between NEXT and the new Stoplight Platform is now you have control over which VCS provider your projects are stored in, making it easier for non-Stoplight users to contribute while continuing to use whatever tools they're comfortable with.

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

## When can I migrate?

If any of the following features are critical to your workflow, we suggest you wait to migrate until we've finished building a solution that fits your needs. You can follow along and even make suggestions by voting on our public roadmap.

**I need to add theming to my documentation**

We are currently developing theming into Stoplight Workspace. _Considering project theming?_

Want to keep up with the development and be notified when this feature is ready? Let us know by voting on our public roadmap.

**I need to show multiple versions of my project's documentation**

We are currently developing support for showing multiple branches in project documentation. This feature will be useful if your project has different branches for each version.

Want to keep up with the development and be notified when this feature is ready? Let us know by voting on our public roadmap.

**I need to customize the ordering of items in my docs sidebar**

Want to keep up with the development and be notified when this feature is ready? Let us know by voting on our public roadmap.

**I need custom HTML, CSS and/or JavaScript**

We are working on a solution for these features in our **short-term roadmap**. For more information, check out this link.

**I need to design shared parameters and responses using the OpenAPI forms editor**

We are working on a solution for these features in our **mid-term roadmap**. For more information, check out this link.

**The discussions feature is a critical part of my workflow**

_TODO: Mid-term roadmap_

**I need lifecycle tags**

_TODO: Mid-term roadmap_

**I need environment variables**

_TODO: Not sure how to phrase this one_

We're considering adding this feature back and would love to hear your use cases. Please let us know how you're currently using this feature and how you expect it to work.

**I need to configure redirects for pages in my documentation**

We're considering adding this feature back and would love to hear your use cases. Please let us know how you're currently using this feature and how you expect it to work.

**I need analytics integrations (GA, Intercom, Segment) in my docs**

We're considering adding this feature back and would love to hear what integrations you need to add. Please let us know my voting on our public roadmap.

**Scenarios are critical to my workflow**

_TODO: Not doing_

**I need to download a static build of my documentation**

_TODO: Stoplight Elements?_

## How do I migrate?

_TODO: Copy some info from https://github.com/stoplightio/proserve/blob/master/next-migration-tool/README.md_

If you feel comfortable, please follow the steps below. If you have any questions, please don't hesistate to reach out and we can schedule time to assist you with this process.

1. Choose which Stoplight project you want to migrate
2. Follow the steps in this article to pull the project contents down to your computer.
3. Create a new project in VCS provider (Github, Gitlab, Bitbucket, etc)
4. Push the contents from your computer into your new project
