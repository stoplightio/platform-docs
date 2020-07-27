---
tags: [Documentation]
---

# Quality API Reference Documentation

Lots of APIs have reference documentation, but it can be tough to make it high quality. 

## Authentication

Make sure the name of all the security schemes in the API overview are human friendly and correctly reflect their purpose. Don't go calling various API keys and access tokens `API-Key-1` and `API-Key-2`, but rather `API-Key` and `APP-ID` might be the way to way to go.

Also try and add descriptions for the authentication to help the user understand and get started with it. For example:

```
Create your own API Key from the user dashboard in the [API Keys](https://example.com/user/api-keys). You'll need an account and an active Pro subscription for the API keys to work.
```

Our [Studio documentation on API Security](https://meta.stoplight.io/docs/studio/docs/Design-and-Modeling/10-api-security.md) has more specifics for various different types of creating and managing various different types of security scheme.

### Names

It's important to have short, human-friendly, and self-explanatory names across your API description.

- Stick to a single dictionary, so either British English, American English, or whichever language best serves your intended audience.
- Avoid Jargon. e.g., Card-number instead of PAN
- Avoid abbreviations e.g., phone-number instead of tel-no
- Stay consistent. 


### Descriptions

Descriptions are a critical piece to create proper documentation. Use these fields across the API description to explain important things to the user. The API designer should have added small descriptions as pointers, but the more detail you go into, the better it is. You can use [Markdown](https://meta.stoplight.io/docs/studio/docs/Documentation/03a-stoplight-flavored-markdown.md) to create informative and aesthetically pleasing descriptions. 


### Other Properties

The "Validations" and "Other Properties" sections in Studio provide important guardrails to the user, resulting in fewer mistakes and a more useful experience when viewing documentation as they won't be forced to guess the possible values of a particular parameter. 

- Choose the correct format. e.g., DateTime/Password
- Provide a default value, which also helps with quick starts in code samples. 
- If there are a set of defined possible values, consider defining an enum. E.g: "status" can only be "pending" or "approved".


### Examples

Examples help the developers learn and try out different use cases. These examples generate better mocks and code-samples too.

- Try using real-life data.
- Test their correctness. Studio should validate these for you automatically 
- Give them explanatory names
- Cover all your essential use cases

### Tags

Tags are used to group your models and endpoints (also known as operations). Various tools will leverage tags in various ways, or not at all, but Stoplight uses them to group operations in the documentation sidebar. 

### SDKs

Stoplight keeps everything, including the OpenAPI in-sync with your Git repo. You can use the OpenAPI spec to generate SDKs if you wish to provide them, using the popular open-source [OpenAPI generator](https://github.com/OpenAPITools/openapi-generator).

- Test SDKs
- Publish to a VCS
- Publish on popular package managers e.g., NPM, PyPi
- Create a page for SDKs in Studio adding with a link to the repository for each platform
- You can also add getting started guides for popular platforms

## Publishing Documentation

With your documentation ready, let users experience it by [sharing it](../1.-quickstarts/share-documentation-quickstart.md). 
