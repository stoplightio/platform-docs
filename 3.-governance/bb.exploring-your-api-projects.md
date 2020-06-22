---
tags: [Governance]
---

# Exploring your API projects

All APIs in your organization, whether internal or external, provide potential business value in terms of new use cases, increased productivity, or visibility. Thus, it is essential to manage all of them. 

Organizations with a growing API stack and team, sometimes being developed in different parts of the globe, it's possible to lose sight of what's already available and its current state. Poor visibility into the currently available APIs leads to inconsistencies and duplication that cost the business dearly. Moreover, the cost of adding a new API into your stack increases exponentially. 

Some common problems that start to surface are:

- Two services solving the same problem pop up - **Multiple points of maintenance, support, and failure without any added value.**
- Two APIs from the same organization responding differently to errors - **Increased cost of support.**
- Inconsistencies in security schemes - **Increased cost of maintenance.**
- Inconsistent documentation and developer experience for APIs - **Developers struggling to use your APIs potentially moving to competitors.**

## Getting started with Explorer 

Explorer is a central repository for all design assets across your organization that would serve as a source of truth for stakeholders in different parts of the API lifecycle. The most crucial step to bringing sense and system to your APIs is to have visibility across all your APIs. Stoplight Explorer makes it easy for you to find, search, and manage your API artifacts. 

After [adding projects](../2.-workspaces/b.adding-projects.md) into your workspace, Explorer analyzes these and makes an indexed, searchable view of your projects. While your teams continue to work in their current workflow, Explorer allows stakeholders to discover and work with multiple assets, keeping them up to date with projects across your organization. 

The different assets that would be discoverable in Explorer are:

- API Descriptions
- Models/Schemas
- Documentation 
- Style guides
- Design documents

With all your API artifacts in a single place, you can use this to:

### Find obscure APIs
*You can't fix what you can't see.* APIs that have long become lost in the organization suddenly become available for developers to use and champions to govern, which helps avoid duplications and remove inconsistencies. Technical writers can improve documentation, API teams can write specs for these APIs which can help your business add value by using what is already available. 
<!--To-do:Add screenshot of explorer search and filter-->

### Promote consistency
When API designers can find existing models and example styles, they build more consistent interfaces. Engineers integrate more quickly, but also they'll have the information to design thoughtful APIs from the start. Technical writers can discover documentation for dor references. API designers can spot inconsistencies in their design and work towards making them consistent. 

With a good view of your current state of design and documentation, you can [create custom style guides](e.style-guides.md) to enforce consistency without drilling down too hard on the current practices. 

Having all these assets discoverable for all APIs allows for the delivery of consistent API design, documentation, code samples, tests, and other essential aspects of operating an API. 

### Visualize Dependencies
Track and visualize inbound and outbound dependencies between your schemas and APIs in the dependencies tab, which helps you keep track of how your changes may affect other dependent services. You can avoid breaking changes and plan versions proactively. Visualizing your dependencies also helps introduce changes that reduce the clutter. 
<!--To-do:Add screenshot of dependency view-->

### Track Changes
Go through changelogs of each asset to keep track of their progress. Inform consumers about changes that might affect them proactively. By using the dependency viewer and changelogs together, make sure all assets are up to date. 
<!--To-do:Add screenshot of changelog-->

### Encourage reuse
Explorer allows users to Star what's important, which enables easy discovery of API artifacts for reuse in future designs. Your technical writers, developers, and designers wouldn't be reinventing the wheel anymore. Technical writers can discover documentation to reuse and repurpose, designers can reuse schemas, and developers can reuse existing APIs in their implementations. 
<!--To-do:Add screenshot of starred view-->

### Share with consumers
Provide role-based access to your consumers in Explorer, providing a single place for your team to work on them while consumers try them out. Get feedback early in your API lifecycle on your new API designs by sharing projects with guests in your workspace. They can read the API documentation, play with the hosted mock server, and even start building out potential solutions. [Add team memebers](../2.-workspaces/d.inviting-your-team.md) to get started. 

