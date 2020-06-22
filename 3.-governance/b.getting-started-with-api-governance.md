---
tags: [governance]
---

# Get Started with API Governance

[API governance](a.overview.md) is being undertaken across companies of all shapes and sizes, but that's not to say that all of them achieve their desired objectives. Some API governance efforts try to standardize too much too soon and create overly restrictive rules which block legitimate work. API development teams then try to circumnavigate thme resulting  in more problems than improvements. To build a successful API governance program, thinking about governance in the right context is paramount. This can usually be solved via cooperation with collaborators from across the organization, surveying them to find and solve legitimate problems that do not slow developers down. There's no single strategy that fits all circumstances and use-cases. Governance is often a balancing act, and it's wise to take a light step-by-step approach. Stoplight Platform arms you with the tooling to help you at each stage of your initiative. 

While a lot of decisions would be taken in the context of your organization, these pointers can help you craft and execute your plan.

#### Identify Goals

Before diving into governance in your organization, it's important to map out your API program's objectives and issues. This could be done by conducting interviews with leaders and stakeholders in the API lifecycle. You could:

- Make an organization chart identifying stakeholders across the organization
- Understand the API roadmap in terms of internal, partner and external services
- Identify issues faced by development teams
- Gather feedback from API consumers
- Identify key goals, e.g., autonomy, agility, control

#### Find Your APIs

A recurring problem that is seen in rapidly growing API programs is not knowing where your APIs are—not knowing what services exist or their current status leads to duplication, inconsistencies, and unanticipated disruptions. *You can't fix what you don't know is broken*. 

Create an inventory of your existing APIs. You can use Stoplight Platform to [add your projects](../2.-workspaces/b.adding-projects.md) from version control or other file systems. Creating this central view is necessary for achieving your governance goals. It's important to get as many of the APIs as you can across your organization into this inventory. 

#### Explore Your Landscape

With your inventory of APIs ready, you can start gauging the current status of your API landscape. Stoplight Platform makes it easy to visualize and rationalize your APIs. After [adding your projects](../2.-workspaces/b.adding-projects.md) to the Explorer you can discover:

- Existing APIs
- API descriptions and the description formats being used, e.g., OpenAPI v3, Postman
- Dependencies between endpoints, models, and articles in your organization
- State of documentation for different APIs
- Security policies being used 
- Changelogs for different versions of APIs and Schemas 

We recommend sharing this information with stakeholders using the Explorer. This information would come in handy in making governance decisions. Learn more about exploring your API landscape [here](bb.exploring-your-api-projects.md)

#### Engage Stakeholders

One of the biggest reasons for inconsistency across your API program stems from teams working in silos, not communicating with each other, or reviewing each other's work. Governance initiatives are most effective when all stakeholders are on board. [Adding team members](../2.-workspaces/d.inviting-your-team.md) like developers, technical writers, product managers, and business leaders into your Stoplight workspace would give them visibility to your APIs and guidelines while bridging the gap between different stakeholders. Having everyone on the same page makes your API program effective and valuable. 

#### Promote Writing API Descriptions

An important discovery while exploring your API landscape is the current state of API descriptions being used in your organization. API descriptions have become an industry-wide practice, and their adoption should be pushed in any organization. You should:

- Evangelize the advantages of creating and updating API descriptions for all existing APIs. [Stoplight Studio](../4.-design/a.overview.md) is a powerful tool to start creating and managing your designs. 
- Converge teams on a single API description format. We recommend moving to OpenAPI v3 due to its extensive support and adoption. 

As your API program matures and adoption for API descriptions becomes common, you can choose to make it mandatory to maintain an OpenAPI v3 for every API. As with most of your governance effort, you should take an incremental approach with this. 

#### Create Style Guidelines 

It's important to standardize your API design to ensure consistency across your APIs. You can start that by [creating style guides](e.style-guides.md) in Stoplight that can be used to validate your API designs. 

While the goal is to have one set of enterprise-wide API governance rules, your learnings from previous steps would help you take a prudent step-by-step approach to this. Gauging what your teams are already doing, start converging them on a set of rules. You can start with a combination of mandatory rules and optional guidelines to help folks make better decisions. 

Examples of rules that you can apply:

- Naming conventions
- Mandatory descriptions for all artifacts
- Mandatory security for all paths
- Only use a type of OAuth as the security scheme

Learn more about [Style Guides](e.style-guides.md).

#### Create a Design Library

Often developers without access to existing resources end up creating duplicate code that leads to inconsistencies and maintenance nightmares. You need to identify reusable design components and put them in a central repository. You can do this by [creating a design library]<!--To-Do: Add link-->() in the Stoplight Platform. This can then be used in APIs across your organization.   

#### Enable API Discovery

As the number of APIs in your portfolio grows, folks need to have an easy way to discover your APIs. To enable this, you should make a catalog of APIs with up to date documentation. 

Using the Stoplight Platform, you can:

- [Create Documentation](../5.-developer-experience/b.getting-started-developer-experience.md) where teams can publish their APIs for internal and external consumption.
- Add team members to your workspace to help them keep track of dependencies using Explorer. 

#### Promote Design-First for New APIs

While enforcing API descriptions for your existing APIs is helpful, the true power of API descriptions is realized by following an [API Design-First](../4.-design/a.overview.md) policy. Designing your APIs before development helps you get quick feedback, lets Frontend and Backend teams work in parallel, and test automatically. Help your architects get started with a new API design by sharing this [guide](../4.-design/b.starting-a-new-api-design.md). 

#### Implement Versioning

APIs often need modifications or sometimes deprecating, and versioning is therefore crucial. It's important to apply your governance rules to ALL the versions, to ensure they're all standardized and properly documented. You can use Explorer to visualize changes between different versions, helping you manage breaking changes.

#### Automate Your Governance Process

Having to rely on your teams to manually apply your API governance rules is no fun for anyone, and not feasible when you're developing APIs at scale. Ensure your API governance rules are met before an API can be deployed. Deploying APIs with governance violations even internally is not recommended.

Stoplight Platform makes this easy along the lifecycle using:
- Automatic Style Guides[creating style guides](e.style-guides.md)
- Contract Testing powered by [automatic mock servers](../4.-design/d.setting-up-a-mock-server.md)

#### Analyze and Improve

Governance is an ongoing initiative. Explorer provides you with a bird's eye view of your landscape that can help you identify gaps and gauge improvements. As you learn from your experiences and add to your initiatives, it helps to:

- Get more stakeholders on board
- Evangelize about your APIs and governance initiatives 
- Gather feedback

> In addition to the current style guide enforcement on an API level, Stoplight Platform would soon have a Quality module that would allow enforcement of guidelines across all APIs. It will also help gauge and monitor the current status of style conformity across APIs.  
