---
tags: [Governance]
---

# Creating a Design Library

## Importance of Consistency

Any organization that has more than a single API should strive for consistency between them. Once a developer has learned the design of an API, they have expectations about the design of another API and might get frustrated when it does not meet these expectations. Hence, being consistent is one of the critical factors in good API design and a cornerstone of excellent developer experience.

Consistency applies on a micro level, for example, using, i.e., camel-case or snake-case everywhere. It also applies on a macro level where it's about the reuse of models. Models can be reused within an API as well as throughout multiple APIs in an organization.

## Common Models

Some domain objects appear in multiple places within an API or in multiple APIs. A typical case is a _Person_ or _User_ object. For example, you may have a project management API with _ToDo_-items assigned to people. Then, you also have a billing API where you can send invoices that have senders and receivers. If two separate teams are working on these APIs independently, you may end up with, for example, one representation of a person with `first_name` and `last_name` and another representation that uses `given_name` and `family_name`, or even just a single `name` attribute.

The result is not only that consumers of both APIs are confused, but also that two teams spent unnecessary time designing what essentially amounts to the same model. While this is a relatively simple example, it's easy to imagine the scale of the problem if it involves a more complex model, and an organization that has not two but many more APIs.

Also, models are not set in stone as new requirements arrive. It's better to maintain changes in one place instead of multiple to ensure consistency throughout time.

## Similar Models

One might argue that not every API requires the same attributes on a model, even if the model describes the same concept. Following up on the previous example, the billing API needs a postal address for each person, whereas the project management API doesn't need it.

In this case, it is useful to think of models as either subsets or supersets of each other. For the described scenario, the project management API's Person model is a subset of the respective model in the billing API, because it contains only some of the attributes.

Not every model is a perfect subset of another. Imagine, for instance, that in addition to the previous example, the Person model in the project management API needs some extra information not required for billing. Both models share some attributes and have some specific fields. Therefore, each of them is a subset of an encompassing abstract Person model that covers every use case.

## Promoting Reuse

To promote the reuse of models in different places, teams should always design their APIs with reusability in mind. When ready, they can publish individual models into a design library. Then, other teams can explore the design library and take what they need for their API design needs. API governance in the organization should ensure that API designers interact with the library.

To account for a scenario in which different APIs need a similar but not necessarily the same model, API designers can attempt to broaden their perspective beyond their API's immediate need. The resulting model becomes a more fleshed-out representation of the domain concept, and no API may use it as it is. Instead, other APIs integrate a subset of the model.

Stoplight has a feature called masking that allows you to include another model and remove some of its attributes, while at the same time keeping the reference to the standard schema. As an additional option, you can modify whether the fields from the referenced model are required or optional.

We cover the usage of the design library, including the masking feature, in more detail later in these docs.