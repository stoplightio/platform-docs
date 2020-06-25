---
tags: [Developer Experience]
---

# Overview

Good Developer Experience (DX) is the key to a useful, usable API. An API could be all-powerful, solving a problem and sublimely implemented, yet it won't matter one bit if users can't figure out how to make it work. The aggregate experience of the user **discovering**, **learning to use**, and finally **integrating** with an API is termed as Developer Experience. DX is the equivalent to User Experience (UX) for your APIs.

### Why does it matter?

DX matters for the same reasons that good UX matters. Users of your API are happier, promote it more, and stay longer when the API has good DX. Your API is a means to an end for the user, and they want to integrate as quickly as possible to move forward in their product development, meaning **they should immediately understand the value and usage of your API**.

### Components of Good DX

#### **A good/consistent API design**

We can't stress this enough; **no amount of documentation can make up for a poorly designed API**. If you haven't already, read more about [designing APIs](../3.-design/a.overview.md). 

#### **Your Audience**

The users of your APIs are primarily two kinds of people:

The **decision-makers** who discover and decide if your API is a good fit to fulfill their use-case. They can be CEOs, CTOs, Product Managers, or Business Executives. 
 
The **developers** who interact with the API to fulfill the use-case. These developers can be internal or external and novice or experienced. Novice developers would usually require more hand-holding while experienced devs would frequently be using your API docs as a reference. 

Your developer experience must cater to both kinds of consumers. You want them to **decide and integrate with ease**. 

#### **API Reference**

An accurate, up-to-date, and detailed API reference is one of the essential pieces of your developer experience. An API reference contains:

- Authentication information
- Endpoint descriptions, parameters, and responses
- Example requests and responses
- Models
- Error messages

#### **Test environment**

Novice developers and non-technical users get up to speed faster by experimenting more than reading. Providing your consumers with a playground inside your documentation is paramount to show them value quickly. It's best to provide them with a sandbox/mock environment that's ready to use.

```json http
{
  "method": "get",
  "url": "todos.stoplight.io/todos"
}
```

#### **Code Samples**

Stack Overflow is a developer's best friend for a reason. Most developers want to jump right into code, so providing them with ready to use samples in their language can lead to happy developers saying wonderful things about you and your API. This also helps avoid mistakes novice developers can make consuming your API - Happy and smaller support teams ;)
<!--
type: tab
title: Python
-->
```python
import http.client

conn = http.client.HTTPConnection("null")

conn.request("GET", "/todos.stoplight.io/todos")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```
<!--
type: tab
title: Ruby
-->
```ruby
require 'uri'
require 'net/http'

url = URI("/todos.stoplight.io/todos")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```
<!--
type: tab
title: Java
-->
```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("/todos.stoplight.io/todos")
  .get()
  .build();

Response response = client.newCall(request).execute();
```
<!--
type: tab
title: C#
-->
```csharp
var client = new HttpClient();

var request = new HttpRequestMessage
{
    Method = HttpMethod.Get,
    RequestUri = new Uri("/todos.stoplight.io/todos"),
};

using (var response = await client.SendAsync(request))
{
    response.EnsureSuccessStatusCode();
    var body = await response.Content.ReadAsStringAsync();
}
```
<!-- type: tab-end -->

#### **Marketing Pages**

Marketing pages are for the business audience. You want these to be high level and clearly show the value your APIs can provide. Focus on the use cases businesses are trying to solve with your API and avoid technical jargon as much as you can. 

#### **Quick Start Guides**

The API reference with code samples is excellent for developers in the later stage of integration. For a newcomer starting with your API, you want to make it easy for them to navigate to creating their first integration. Developers learn best by doing. Create a quick start guide with the minimum steps required to perform the first action with your API. This can be a step-by-step guide on authentication, calling your most straightforward endpoint fulfilling the most common use case. Do not forget the code samples for these steps, and keep it easy.  

#### **Tutorials**

While your API is used by developers to fulfill many use cases, there are always some that are more popular. It's best to identify those and create a tutorial for them. The description of steps should be easy to follow and concise. Clarity and brevity support the learning process and are a best practice for all kinds of documentation. It's also useful to create a sample application that you can add to GitHub. 

#### **Changelog**

The Changelog section of your API documentation lets your users know how stable your API is. It also lets them know if anything's changed, in the instance that one of their calls stops working. These are also very helpful for existing users migrating to a newer version of your API. You can take a look at [GitHub's changelog](https://developer.github.com/changes/) for an example of thorough changelog documentation. Stoplight Platform automatically generates changelogs for your Artifacts that can be used to keep these up to date. We'll talk about this in detail later. 

#### **Terms of Use**

Terms of Use are the legal agreement between you and your users. In the Terms of Use section of your API documentation, you should include API limits, constraints, branding guidelines, and what usage is acceptable. Transparency goes very well with users, especially technical audiences. Developers love knowing everything. So, be very clear in what the terms and conditions are, avoiding putting these critical points in fine-print. 

#### **Status Page**

It's never pretty for developers trying to interact with your API and facing errors that they can't put a reason to. Being clear about the current status of your service is very helpful. You can use a service like [Statuspage](https://www.statuspage.io/) to create one or build it yourself and make it part of your DX offering. 

#### **Software Development Kits (SDKs)**

With your previous steps sorted, it always helps to reduce the redundant tasks that a developer needs to perform. For that, providing SDKs in popular languages helps keep your developers happy and productive. With an OpenAPI description ready and validated by Stoplight tooling, you can use this to generate and publish SDKs without much extra work. We'll stick to our promise of not locking you down in our platform and letting you use all the fantastic tooling out there. 

Ready to get started checking these boxes with Stoplight? [Get Started](b.getting-started-developer-experience.md)

### Make your APIs discoverable

Well, if the right people can't find your API documentation easily, there's not much use of having a fantastic developer experience. You can use project visibility settings to create internal, public and private documentation.
 
To make your APIs discoverable get started [here].(../1.-quickstarts/share-documentation-quickstart.md). 
