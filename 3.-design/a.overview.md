---
tags: [Design]
---

# Overview

Stoplight has an editor called [Stoplight Studio](https://stoplight.io/studio), which doubles as both a Markdown editor, and a visual API Designer. An API designer is a piece of software which helps you work with API Descriptions, specifically the most popular formats: OpenAPI (both v2 and v3), and AsyncAPI. 

## What is an API Description

API Descriptions usually take the form of a YAML or JSON document, which can explain the "I" part of API: the interface. This covers HTTP methods, endpoints, headers, authentication schemes, request bodies, example responses, and every other part of an API, including callbacks and webhooks!

For years folks would be stuck writing this YAML or JSON by hand in a text-editor, but API Design software like Stoplight Studio aims to make that be a thing of the past, providing a graphical interface that reduces the redundancy of working with plain text. 

## API Design-First

API descriptions can be created before you build an API, or afterward. In ye olden times, people would build a whole API, put it into production, then think, "oh, I should probably write some documentation." You can do that with Studio if you like, but there is another way.

API Design-First is the concept of planning out the API before you build it.  Instead of doing that in some Google Document or on the back of a napkin, you can do it in a reusable, machine-readable format which can power functionality at every stage of the API lifecycle:

1. **Generate Documentation** - beautiful API reference documentation
2. **Mock Servers** - get API consumers feedback from simple prototypes
3. **Request Validation** - why write all that validation logic more than once
4. **Contract Testing** - ensure the API is doing what it says it should be doing
5. **Code Generation** - computers have learned to program themselves
6. **SDK Generation** - let API consumers talk in their programming language of choice
7. **Server Stubs** - generators can do the application boilerplate for developers

With an API Design-First strategy in place, you can...

#### Get Early Feedback

When an API has been designed upfront, API consumers get a chance to play with an automatically generated mock server, which helps you get quick feedback. This ensures that the API that you're building fulfills consumer requirements without spending any time and cost on development. It also saves your consumers from unanticipated breaking changes later. 

#### Reduce Cost

Catching potential problems for clients early on avoids wasting time and money writing code which is not going to solve a problem. These early iterations are a game-changer because changing the API description takes minutes, not hours or days! It also reduces the chances of noticing major issues shortly after v1 launches, meaning you can put off v2 and v3 for a while, maybe indefinitely.

What is the cost of a bad API? Try multiplying all of your tech debt by your number of API consumers.

#### Put Consumers First

Getting started with implementation tends to couple your solution with the technology. Designing your API first ensures your solutions are technology agnostic and built with a greater number of consumers in mind.

#### Ensure Consistency

Consistent APIs that follow industry best practices and are in line with other APIs in the organization lead to development that is efficient and less prone to errors. API descriptions can be automatically validated against style guides to ensure it follows best practices and organization standards, leading to good developer experience. By designing the API first, you can validate early, thus avoiding changes once API has been developed or even worse is being used by consumers.   

#### Develop in Parallel

Creating and finalizing a contract early-on allows teams across your organization to work simultaneously without having to wait for the development stage of the API to complete. The generated mock server can be used to test API dependencies, helping develop front-end or back-end applications that consume these APIs, which leads to increased productivity and efficiency. 

#### Develop Faster

You can generate server-side stubs and contract tests that take away the redundant work from your API developers while ensuring the APIs get developed correctly. [OpenAPI.Tools](https://openapi.tools/#server) has a list of tools to serve your need for server-side stubs. 

#### Validate and Test Efficiently

Your API implementation can be validated automatically against your API description. Requests coming in from applications consuming your API are also validated, which ensures the API implementation and applications get built correctly without introducing any dependency between various teams. 

#### Provide a Good Developer Experience

A design-first strategy ensures an up to date API description, consistent design, comprehensive documentation, and well thought out examples. This, in turn, can be used to generate beautiful interactive documentation that makes it easier for developers to use your API. As the design is the source of truth, it ensures the documentation is correct and always up to date. The same API description can then be used to generate code samples and SDKs, improving your developer experience further with little effort.

#### Get to production faster

Early feedback, parallel development if API server and API consumer, maybe even server code generation, and comprehensive contract testing all ensure that you get to market faster, beating your competition both in quality and speed. 

## Stoplight Studio

Stoplight Studio comes in two flavors:

- Studio Web - A module available as part of Stoplight Platform
- Studio Desktop - A downloadable desktop application for offline use, supporting macOS, Windows and Linux

They both do the same job: help you create and modify content in your workspace's projects, and push changes back. Stoplight Studio chooses to do away with awkward two-way syncs introduced by some tools, and sticks to tried and tested Git-based workflows.
