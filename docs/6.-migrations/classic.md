# Migrating from Classic (app.stoplight.io)

## Introduction

One of the main goals for this new version of the Stoplight Platform has been to make it easier for you to integrate Stoplight into your existing git workflows. In Classic, projects were hosted in the Stoplight cloud with no connection to git.

## When can I migrate?

While the new Stoplight Platform includes a lot of new functionality, there are some features from Classic that have not yet made their way over. We are taking this opportunity to re-imagine and improve the functionality listed below, and will be rolling it out through the rest of the year. If any of the features below are critical to your workflow, we suggest that you wait to migrate until the relevant features are released. You can continue to use Stoplight Classic without distruption until then.

Each feature is linked to a card on our public roadmap, and we encourage you to follow the features relevant to you - we'll notify you as each is released.

|                                     |  Timeline   | Description                                                                        |
| ----------------------------------- | :---------: | ---------------------------------------------------------------------------------- |
| [Docs: Theming](https://roadmap.stoplight.io/c/52-theming-and-branding)                       |  Immediate  | Customize the branding and colors                            |
| [Docs: Versioning](https://roadmap.stoplight.io/c/60-multiple-branches)                    |  Immediate  | Show/hide specific branches in each project's docs                                 |
| [Docs: Table of contents ordering](https://roadmap.stoplight.io/c/59-customize-docs-sidebar-ordering)    | Short-term  | Completely custom ordering of your docs sidebar. By default, files will be organized alphabetically, matching the order in the filesystem                                     |
| [Docs: Custom CSS, JS, and HTML](https://roadmap.stoplight.io/c/57-embeddable-component-library)      | Short-term  | Rich component library for creating custom API docs site                              |
| [Design: Shared parameters/responses](https://roadmap.stoplight.io/c/10-openapi-shared-components) |  Mid-term   | Form based editing for OpenAPI shared components                                   |
| [Design: Lifecycle tags](https://roadmap.stoplight.io/c/65-lifecycle-tags)              |  Mid-term   | Add tags to build workflows around your API lifecycle                               |
| [Docs: Try It OAuth token generation](https://roadmap.stoplight.io/c/58-request-maker-authentication)   |  Mid-term   | Generate OAuth 1 & 2 tokens for HTTP requests in Try It                             |
| [Discussions](https://roadmap.stoplight.io/c/61-discussions-comments)                         |  Mid-term   | Create and resolve discussions on API designs and docs                             |
| [Docs: Custom variables](https://roadmap.stoplight.io/c/47-custom-variables)              | Considering | Allow users to set a variable once and have it used everywhere                       |
| [Docs: Redirects](https://roadmap.stoplight.io/c/68-redirects)                     | Considering | Automatic redirects when docs routes are changed                                   |
| [Docs: Integrations](https://roadmap.stoplight.io/c/64-analytics-integrations)                  | Considering | First class support for integrations like Google analytics, Segment, Intercom, etc |
| [Design: CRUD Builder](https://roadmap.stoplight.io/c/63-crud-builder)                | Considering | Automatically generate a list of CRUD endpoints for a schema                       |
| [API Discovery](https://roadmap.stoplight.io/c/66-learning-recording)                       | Considering | Automatically create an OpenAPI document by proxying requests to an existing API                                                         |

## How do I migrate?

1. Open the Stoplight project you want to migrate in Stoplight Classic
2. Export the OpenAPI v2 file with Stoplight extensions
3. Create a new project in Stoplight Platform
4. Import the file into the new project
5. Promote to a git repo

<!-- TODO: Would be nice to convert text sections to markdown files -->
<!-- TODO: Images (2) and link to relevant docs articles (3) -->

## FAQ
