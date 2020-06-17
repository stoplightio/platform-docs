# Migrating from Classic (app.stoplight.io)

## Introduction

One of the main goals for this new version of the Stoplight Platform has been to make it easier for you to integrate Stoplight into your existing git workflows. In Classic, projects were hosted in the Stoplight cloud with no connection to git.

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
| Docs: Custom variables              | Considering | Allow users to set variable once and have it used everywhere                                                                              |
| Docs: Redirects                     | Considering | Automatic redirects when docs routes are changed                                                                                          |
| Docs: Integrations                  | Considering | First class support for integrations like Google analytics, Segment, Intercom, etc                                                        |
| Design: CRUD Builder                | Considering | Automatically generate a list of CRUD endpoints for a schema                                                                              |
| API Discovery                       | Considering | Automatically create an OpenAPI file by proxying requests through an existing API                                                         |

## How do I migrate?

1. Choose which Stoplight project you want to migrate
2. Export the OpenAPI v2 file with Stoplight extensions
3. Create a new project in Stoplight Platform
4. Import the file into the new project
5. Promote to a git repo

<!-- TODO: Would be nice to convert text sections to markdown files -->
<!-- TODO: Images (2) and link to relevant docs articles (3) -->

## FAQ
