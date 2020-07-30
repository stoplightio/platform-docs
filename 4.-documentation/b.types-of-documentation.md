---
tags: [Documentation]
---

# Types of Documentation

When people think of documentation for an API they often think of API Reference Documentation, but they are only one of several types of documentation that your API consumers will need to solve various use-cases. You'll also want Quick Start Guides, How-To Tutorials, and interactive documentation, all of which are supported in Stoplight, including API Consoles and automatic sample code.

We'll quickly go over the why, what, and how of these types of documentation, to help you make the best developer experience for anyone using your API.

## API Reference

API Reference Documentation has a couple of simple goals:

- Help developers understand what’s possible with your API
- Show developers how to move from documentation to code

This documentation focuses on all the endpoints (a.k.a "operations") available in an API, and helps explain potential input and output values that can be in requests and responses. Some API reference documentation will just show an example, but it's more useful to expand upon that and explain not just what those values mean, but what other values could also be valid in various contexts.

Stoplight automatically generates an API reference from your API descriptions, so if you have an OpenAPI document, you'll have API Reference documentation created for you whenever the project is analyzed. By reusing request and response examples that exist, or creating examples from default and example property values, it's possible to create high-quality API reference documentation without manual effort.

> If you don't already have an API description, get started by [creating a new API design](../3.-design/b.starting-a-new-api-design.md) or convert some other machine-readable formats like RAML, HAL, or Postman, to OpenAPI with [Apimatic Transformer](https://www.apimatic.io/transformer/).

Stoplight groups them by tags and uses their summary in the sidebar, then shows off all the request and response information, with a bunch of the important validation highlighted. If a property has to be a number, and has a minimum value, has to be an email address, or a date-time, then it will show in the generated docs.

This documentation is also where you show users which endpoints need which authentication methods (or security schemes), what cache headers they could expect to find, and even point out things like pagination. Many of these topics would also make for a good tutorial too, to introduce the concepts and explain any gotchas or non-standard bits.

Read our guide [Quality API Reference Documentation](https://meta.stoplight.io/docs/studio/docs/Documentation/01-getting-started.md) to see how to make them the best they can be.

## Quick Start Guides

Let's assume you've done a great job of designing your API, named your endpoints in a friendly and consistent way, picked a common message format like JSON:API, and are using a popular authentication method like OAuth 2.0. That should be enough to get a developer started, right?

Maybe, maybe not. Even the best designed APIs with the most robust references should provide a Getting Started Guide to point developers in the right direction. Many developers may be new to many of the tools and standards you have chosen to use, they may even be new to consuming API's in general! Walk them through the most common tasks, identify the steps to authenticate, and show off a step by step guide to help them get their first "aha" moment: usually creating a resource on the server, or some other successful transaction.

Once you've written this guide, make it highly visible within your documentation. Send it to new developers in an email when they sign up for security credentials in case they miss it. In removing any possible obstruction between new developers and their first successful experience, you'll have more successful integrations with your API, which hopefully means more money, or more happy users.

Check out our quick-start guide on [creating Documentation with Studio](https://meta.stoplight.io/docs/studio/docs/Documentation/01-getting-started.md).

## How-To Tutorials

Tutorials are similar to getting started guides but are looking to make it easy to perform a particular use case. You can create a tutorial folder, and add more articles to it covering extra topics as questions come in. 

For example, things like pagination are somewhat covered in API Reference Documentation. Maybe a query string parameter exists like `?page=1` or `?cursor=s24dfkjfhkdf`, and whilst some developers might understand that perfectly, many won't. A tutorial for how pagination works for your API is a great place to explain why you chose your specific pagination approach [of the many that exist](https://www.citusdata.com/blog/2016/03/30/five-ways-to-paginate/), and explain how your users should interact with it. E.g.: [Slack](https://api.slack.com/docs/pagination) and [Stripe](https://stripe.com/docs/api/pagination).

Other common tutorials are "Common Errors" which explain how your [error objects](https://apisyouwonthate.com/blog/creating-good-api-errors-in-rest-graphql-and-grpc/) work, what common status codes mean so you don't need to document 500, 501, 502 on every single operation, and any other useful information that can help users troubleshoot trouble.

Within Stoplight there is no difference between a getting started guide, a tutorial, or any other sort of Markdown article, so check out our quick-start guide on [creating Documentation with Studio](https://meta.stoplight.io/docs/studio/docs/Documentation/01-getting-started.md).

