---
tags: [Documentation]
---

# Getting Started with Developer Experience

### Creating your API reference

Stoplight automatically generates an API reference from your API description. 

> If you don't already have a API description ready, get started by [starting a new API design](../3.-design/b.starting-a-new-api-design.md).

It's essential to populate and validate various parts of your API description to create a top-notch API reference. Open up your API in Studio and let's start going through the pieces required to take your docs up a notch:

#### Authentication

- Make sure the name of all the security schemes in the API overview are human friendly and correctly reflect their purpose. For example:

 *Your API uses a combination of API keys. You don't want to name them `API-Key-1` and `API-Key-2` rather `API-Key` and `APP-ID` might be the way to way to go.*

- Add a description for the auth to help the user understand and get started with it. For example:

 *You can generate this API-Key from [https://link-to-apikey-generation]()*

> **Note:** Do the same for security schemes on the endpoint level if they exist.

#### Names

It's important to have short, human-friendly, and self-explanatory names across your API description. 

- Stick to American English. e.g., Airplanes instead of Aeroplanes
- Avoid Jargon. e.g., Card-number instead of PAN
- Avoid abbreviations e.g., phone-number instead of tel-no
- Stay consistent. 

Applies to: `Endpoint` , `Endpoint Parameters` (Path, Header, Query), `Request Body`, `Response Fields`, `Models`, `Model Fields`, `Examples`

#### Descriptions

Descriptions are a critical piece to create proper documentation. Use these fields across the API description to explain important things to the user. The API designer should have added small descriptions as pointers, but the more detail you go into, the better it is. You can use [Markdown](https://meta.stoplight.io/docs/studio/docs/Documentation/03a-stoplight-flavored-markdown.md) to create informative and aesthetically pleasing descriptions. 

Applies to: `Endpoint` , `Endpoint Parameters` (Path, Header, Query), `Request Body`, `Responses`, `Response Fields`, and `Models`

#### Other Properties

The "Validations" and "Additional Properties" sections provide important guardrails to the user, resulting in lesser mistakes and pleasant experience in general. You don't want the user to be guessing the possible values of a particular parameter. 

- Choose the correct format. e.g., DateTime/Password
- Provide a default value, which also helps with quick starts in code samples. 
- If there are a set of defined possible values, consider defining an enum.
- Provide pattern, the number of properties, and length validations where they apply. For example, a string can't be greater than eight characters. 

Applies to: `Endpoint Parameters` (Path, Header, Query), `Request Body`, `Response Fields`, `Models`, `Model Fields`

#### Examples

Examples help the developers learn and try out different use cases. These examples generate better mocks and code-samples too.

- Try using real-life data.
- Test their correctness. Studio should validate these for you automatically 
- Give them explanatory names
- Cover all your essential use cases

Applies to: `Endpoint Parameters` (Path, Header, Query), `Request Body`, `Response`, `Response Fields`, `Models`, `Model Fields`

#### Tags

Tags are used to group your models and endpoints. While you can take any approach, it's useful to group them according to use cases. 

#### Experimentation Environment

*Try it* functionality is automatically added to all endpoints. The users can navigate to any endpoint to test it out with different values. The users also get the ability to try out a mock server in case they don't have access to the live API. Make sure all environments (Production, Sandbox) are added to the servers in the API overview, and they have friendly names associated with them. 

**Code Samples**

Code samples are generated in popular platforms and available under the `Try it` tab. Having good examples and validations leads to better code samples.

### Creating Reference Documentation

#### Overview

These pages are used to signify the major components of your platform. Cover on a high level what the platform can do and how this differentiates from your competitors. This is primarily directed towards decision-makers looking to fulfill a use case through your API. Using Studio, you can use Markdown to create a visual + descriptive overview page with links to other components of your developer portal. 

- Add visuals
- Have CTAs linking to components of the dev portal e.g., Quick Start Guides

#### Quick Start Guide

A quick start guide is usually a single article that you can create for each API. As you are targeting first-timers with this article, choose your easiest and most common use case. Create a new article in Studio and start with a basic overview of the platform. Then follow with a step to step guide:

- How to register? This can contain a link to generating an authentication token or API key.
- How to authenticate using the generate credentials?
- Calling your first endpoint. e.g., Sending your first message
- Add an HTTP request maker for each step allowing users to test and copy code samples.
- Provide easy to use examples.

#### Tutorials

Tutorials are similar to getting started guides but are looking to make it easy to perform a particular use case. You can create a tutorial folder and add articles to it. Follow the same guidelines as quick start guides for this skipping the basic steps. Assume the user already has registered, learned how to authenticate, and is looking to solve a particular use case. 

#### Changelog

Explorer automatically creates changelogs for all your APIs. Creating a changelog is as easy as using the changelog generated by Explorer, putting it into an article, and adding any other pointers that you want. Make sure you update your changelog as your API updates. It's normally recommended to keep a single article adding a section for each version. 

- Use headings for different versions to allow easy navigations
- Use tags to specify kinds of changes. Some examples are: `breaking,` `feature,` `bug-fix,` `improvement.`

#### Terms of reference

Create an article covering:
- API limits
- Constraints
- Branding guidelines
- Any other limitations or Terms of use

Terms of reference are usually added at the top level after the API reference. 

#### SDKs

Stoplight keeps everything, including the OpenAPI in-sync with your Git repo. You can use the OpenAPI spec to generate SDKs if you wish to provide them, using the popular open-source [OpenAPI generator](https://github.com/OpenAPITools/openapi-generator).

- Test SDKs
- Publish to a VCS
- Publish on popular package managers e.g., NPM, PyPi
- Create a page for SDKs in Studio adding with a link to the repository for each platform
- You can also add getting started guides for popular platforms

### Publishing Documentation

With your documentation ready, let users experience it by [sharing it](../1.-quickstarts/share-documentation-quickstart.md). 
