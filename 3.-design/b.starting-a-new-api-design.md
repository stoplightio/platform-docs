---
tags: [Design]
---

# Start a new API design

Following the [API Design-first](./a.overview.md#API-Design-First) workflow, you are creating an API Descriptions before the API exists. This can be a bit daunting at first, but grab a whiteboard, notepad, or however you like to keep notes, and lets think about what this API is going to do.

## Define the intent of the API

The first step to making a new API is defining the purpose of the API. Typically you'd work with various stakeholders in your organization to define abstract requirements and the type of consumers (Internal, Partner, or External) it would cater. 

For example, you could be:

- Solving a use-case for external customers that will not effect internal systems
- Providing a reusable service for use across your organization
- Creating a unique integration API for a single partnership
- Splitting an internal monolith into microservices
- Glueing some internal microservices into a monolith

Depending on the scope of this API, the API design process begins by finding out the critical consumers for this API.

## Understand your consumers

The goal is to provide an API that solves consumer problems in the most efficient way, but how you go about designing the API will depend on a few things.

This could be achieved by sending out a survey to your consumers to understand their needs. Do this with a few key consumers covering a range of use cases, preferably. The questions you could be asking are:

- What are the key business needs and workflows you are trying to solve?
- What existing APIs are you talking to, if any?
- What platform will you be creating this for, mobile, web, backend?
- What data will you keep copies of locally, vs. referencing from the API?

The responses to these questions should get you thinking about how an API needs to function, and knowing what sort of clients you're primarily dealing with can help think about the size of payloads. 

For example, if it's primarily backend services and web-apps then HTTP/2 multiplexing is a great option. The API can contain a larger number of endpoints with vary levels of cacheability, no longer constrained by "number of requests" being a limiting factor due to the nature of HTTP/2 multiplexing and Server Push.

Conversely, if the API is serving mostly clients on low latency networks, a more traditional approach could be taken where HTTP/1.1 style "mega endpoints" are used to keep the number of requests down.

A typical output of this exercise would be detailed requirements of the API and a user persona that would act as your reference when designing your API. 

## Explore Existing APIs

Sometimes organizations end up creating similar services to solve similar problems, which is usually down to teams simply not knowing what other teams are working on, leading to inconsistencies, code duplication, and wasted time. Seeing as time is money, it's ideal to do the least work to solve the problem.

Use the Explorer in your Stoplight workspace to find any endpoints that can fulfill this use-case or can help you in solving it. You could find an endpoint that:

- Solves a similar use-case; You can use it as a reference to design your API.
- Helps you solve a part of the use-case; Share it with the developers. They can use it in implementation.
- Solves the use-case completely; Share it with the stakeholders.
 
Found something useful? Click the Star! 

## Find Reusable Models

Now that you have your requirements in order and list of services that you can reuse. It's time to think about the resources that need to exist. You can access models across your organization from the Explorer. 

We need a *Passenger* resource, so search for an existing *Passenger* model.

We need a *Flight* resource, so search for an existing *Flight* model.

If you find some shared models that roughly describe how you think your resource should look then great, you've saved yourself some work! Click the Star, and we can use them later. Don't worry about models that have an extra or a missing field. The Studio has you covered! 


## Design the Interface

With your requirements ready and a list of reusable resources handy in the Explorer, jump into Studio and create a new project. 

Get started by creating an API. Give it a title and a description. There are other essential fields in the API overview, but you can come back to them later. 

### Set up Security

API security schemes protect your API resources by authenticating apps or users that consume your API. There are a number of standard authentication protocols you can pick from, each with their own strengths and weaknesses. 

It's recommended to choose an authentication type that is already being used in other APIs in your organization. This promotes ease-of-use and consistency for developers consuming different APIs. Read more about security [here](https://meta.stoplight.io/docs/studio/docs/Design-and-Modeling/10-api-security.md).

### Create Models

Hopefully, from the last exercise, you have a list of models you need to fulfill the use-case. Let say you are creating an API that manages passengers on a flight. 

You need a *Flight* and a *Passenger* model for this API. You already found a *Flight* model in the Explorer. Let's create a *Passenger* model. 

- Start by creating a new model. Give it a name and define tags. Tags are used to group models in an API, which makes it easier for users to find them. 

Before you save it, take a look at how naming and tagging is done in your organization in the Explorer. Make sure you're consistent with that. You can make rules for this by creating [custom style guides](../4.-governance/d.style-guides.md) to enforce it automatically.

- Next, add a field to the model. Give it a name, a short description, and choose a type. You can either use a native type or refer to another model using `$ref`. 
- Add validations to enforce constraints or formats on data like enums or DateTime. These validations provide the user with the required context and guardrails to reduce mistakes. 

Repeat this with all the fields. Again, keeping an eye on your organization's standards is essential.

- Next, add examples, which are vital for mocking and documentation. Use a real-life example to give the best experience for consumers and technical writers who'd be building upon these later. 

With your model ready, you are all set to create an endpoint. 

### Add Endpoints

- Using pluralized names in paths is recommended, e.g., `/passengers` but take a look at how it is done in your organization. You want it to be consistent. 
- Give a friendly name to the HTTP actions. Let start with *Get Passengers*.

Next, add request parameters. You can add Path, Query, and Body parameters. 
- Add parameters, choose a type, and add short descriptions. Validations like in models are essential to add additional constraints. 

Finally, let's use the model we created as the response type. 
- Using references lets you reuse models across multiple endpoints. You can also use existing models from other APIs. 
- It's easy to skip errors, but they are important. Proper error handling saves loads of support time and frustrated developers.
- You should add examples for each response type.  

You just designed your first endpoint. Preview how it would look to consumers. Repeat with other endpoints. 

## Linter Guidance

While you're busy designing your APIs, Studio validates your designs on the fly. Keep a lookout on the side for warnings and errors. It would point out if you made any mistakes like a missing description or skipping a response. 

By default, linting is done based on a predefined ruleset. Are you having trouble spotting inconsistencies in your design particular to your organization? [Create a custom style guide](../4.-governance/d.style-guides.md) to define rules that are specific to your organization. Some example rules can be:

- `Enforce` having at least one global security scheme
- `Warn` against using an authentication except for OAuth
- `Recommend` having at least one error for Endpoints

These rulesets give you the ability to define and promote consistency across your organization automatically with flexibility. 

## Plan Documentation

Documentation is a very important part of the API lifecycle and should start early in the design phase. Write short descriptions across all artifacts that technical writers can build upon. Add examples that give pointers on how they might be used. 

With your design in shape, share it with technical writers early so that they can start writing the docs. You can also share relevant articles from Explorer with tech writers. The Explorer will let all stakeholders stay up to date with how the API is coming along. 

While Studio is good at helping designers write API descriptions, it is also built to support writing markdown documentation. [Get started with Documentation](../5.-developer-experience/b.getting-started-developer-experience.md)
