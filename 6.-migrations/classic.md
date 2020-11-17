# Migrating from Stoplight Classic

## Introduction

One of the main goals for this new version of the Stoplight Platform has been to
make it easier for you to integrate Stoplight into your existing Git-based
workflows. In Stoplight Classic, projects were hosted in the Stoplight cloud
with no connection to Git. With the latest version of Stoplight, all of your
designs and related assets can be fully managed directly in your Git VCS
provider.

## When can I migrate?

While the new Stoplight Platform includes a lot of new functionality, there are
some features from Classic that have not yet made their way over. For a full
feature parity breakdown, please review the guide
[here](https://support.stoplight.io/hc/en-us/articles/360035390511-What-are-the-differences-between-the-Stoplight-products-).

Below are several features that were available in Classic that are linked to our
upcoming roadmap. We encourage you to follow the features relevant to you -
we'll notify you as each is released.

|                                                                                                       |  Timeline   | Description                                                                        |
| ----------------------------------------------------------------------------------------------------- | :---------: | ---------------------------------------------------------------------------------- |
| [Docs: Custom CSS, JS, and HTML](https://roadmap.stoplight.io/c/57-embeddable-component-library)      | Short-term  | Rich component library for creating custom API docs site                           |
| [Design: Shared parameters/responses](https://roadmap.stoplight.io/c/10-openapi-shared-components)    |  Mid-term   | Form based editing for OpenAPI shared components                                   |
| [Design: Lifecycle tags](https://roadmap.stoplight.io/c/65-lifecycle-tags)                            |  Mid-term   | Add tags to build workflows around your API lifecycle                              |
| [Docs: Try It OAuth token generation](https://roadmap.stoplight.io/c/58-request-maker-authentication) |  Mid-term   | Generate OAuth 1 & 2 tokens for HTTP requests in Try It                            |
| [Discussions](https://roadmap.stoplight.io/c/61-discussions-comments)                                 |  Mid-term   | Create and resolve discussions on API designs and docs                             |
| [Docs: Custom variables](https://roadmap.stoplight.io/c/47-custom-variables)                          | Considering | Allow users to set a variable once and have it used everywhere                     |
| [Docs: Redirects](https://roadmap.stoplight.io/c/68-redirects)                                        | Considering | Automatic redirects when docs routes are changed                                   |
| [Docs: Integrations](https://roadmap.stoplight.io/c/64-analytics-integrations)                        | Considering | First class support for integrations like Google analytics, Segment, Intercom, etc |
| [Design: CRUD Builder](https://roadmap.stoplight.io/c/63-crud-builder)                                | Considering | Automatically generate a list of CRUD endpoints for a schema                       |
| [API Discovery](https://roadmap.stoplight.io/c/66-learning-recording)                                 | Considering | Automatically create an OpenAPI document by proxying requests to an existing API   |

## How do I migrate?

Because we've updated our approach to where your data is stored and managed
(your VCS rather, than our homegrown backend), this migration is a bit more
involved. The goal of this migration is to move your data from Stoplight Classic
to Git repos in your VCS, and then to connect those Git repos to your new
Stoplight Workspace.

If you have not already done so, you can create a free Stoplight workspace
[here](https://stoplight.io/welcome).

> If you feel comfortable and ready to migrate, please follow the steps below.
> If you have any questions concerns, please don't hesitate to [reach
> out](mailto:support@stoplight.io).
### Migrating project contents

First, let's export the contents from one of your Classic projects.

1. Choose which Classic project you want to migrate.
2. Follow [this
   guide](https://help.stoplight.io/docs/design/exporting-to-swagger-or-raml) to
   export the project's **OpenAPI v2 file with the Stoplight extensions
   included**. If you have multiple versions, you'll want to export each one
   individually.

Now that you have the exported OpenAPI file(s), you can now add them to a Git
repository which can then be added to your new Stoplight Workspace.

1. You can choose to either create a new Git repository or import the file to an
   existing one. Follow [this
   guide](../1.-quickstarts/add-projects-quickstart.md) to learn how.

> If you are interested in upgrading from OpenAPI v2 (otherwise known as
> Swagger) to the latest OpenAPI v3 format, there is free conversion tool
> available [here]( https://www.npmjs.com/package/swagger2openapi). The latest
> version of Stoplight Studio supports either format.

## FAQ

The concepts in the new Stoplight Platform should be very similar to what you're
used to in Classic. Here are some commonly asked questions to help clarify those
similarities and differences. If you have any additional questions, please don't
hesitate to [contact us](mailto:support@stoplight.io).

**Is a Stoplight Workspace similar to a Workspace in Classic?**

Yes, they are very similar. Just like in a Classic workspace, your workspace is
where you'll invite members, add projects, and create a billing subscription.

**How do the members roles compare to the ones in Classic?**

The roles and permissions work similar to Classic, but some of the role names
have changed.

Below is a mapping of Classic to Platform roles:

| Stoplight Classic | Latest Stoplight |                                   |
| ----------------- | ---------------- | --------------------------------- |
| Owner             | Owner            | Can change workspace settings     |
| Admin             | Admin            | Can manage members                |
| Member            | Maker            | Can add projects                  |
| Guest             | Viewer           | Can view projects                 |
|                   | Guest            | Can be granted access to projects |

**How do I publish my API documentation?**

In the new Platform, API documentation is automatically generated from the files
in your projects. You control access to projects by configuring the project's
visibility settings.

For example, if you want a project to only be visible by Workspace members, you
can set the project's visibility to `internal`. You can also give members and
guests explicit access to view specific private or internal projects.

**How do I update the contents of my project's documentation?**

When adding a project to your Stoplight Workspace, a webhook will be installed
within the Git repository. This allows Stoplight to automatically update your
documentation when any of the API design assets in the repository have changed.

The contents of the project can then be updated from any one of your favorite
tools, such as Stoplight Studio or even directly in the VCS provider. As long as
the changes are pushed to the Git repository, they will be automatically synced
with your Stoplight Workspace.

If you need more control over when documentation is updated, see our publishing
guide [here](../2.-workspaces/g.automating-publishing.md).

**How do I add a custom domain to my documentation?**

To configure a custom domain for your workspace, please review the guide
[here](../2.-workspaces/j.custom-domains.md).

**How do I configure authentication such as Auth0 or SAML?**

To configure a custom SSO provider for your workspace, please review the guide
[here](../2.-workspaces/e.configuring-authentication.md).

**How do I create a new version of my API project?**

Versions in Stoplight are now managed through Git branches. For more information
on this subject, please review the guide
[here](../2.-workspaces/h.branch-management.md).

**How do I configure a Prism mock server?**

Similar to Classic, every OpenAPI file in your Workspace has a mock server
configured automatically. All you need to do is send requests to the API's
unique mock URL. For more information, please read this [guide on mocking in
Stoplight](../3.-design/d.setting-up-a-mock-server.md).
