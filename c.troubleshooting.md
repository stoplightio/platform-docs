# FAQ

Below you will find answers to commonly encountered questions.

> If you are having trouble and cannot find a suitable answer, don't hesitate to [let us know](mailto:support@stoplight.io).

## Why is there an "Others" section in the sidebar?

If you're seeing an "Others" section in the sidebar of your project documentation...

![Others](assets/images/others_missing_tag.png)

Grouping of endpoints and models is done with [tags](https://swagger.io/docs/specification/grouping-operations-with-tags/). To prevent an "Others" section from being generated, be sure to add at least one tag to each endpoint and model in your project.

You can find more information on the default order of the project sidebar (as well as how to customize it) [here](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md).

## How do I export a file from Stoplight?

If you need to retrieve a file published in Stoplight, the quickest way to do so is using the **Export** buttons found in both Explore and your project documentation.

***Exporting using Explorer***
![Export through Explorer](assets/images/export_explorer.png)

***Exporting within Studio***
![Export through Studio](assets/images/export_studio.png)

### What are the differences between Original, Bundled, Dereferenced.
1. Original - is the raw file keeping the $refs
2. Bundled - only resolves remote $refs 
3. Dereferenced- resolves all remote and inline $refs

## Does Stoplight support adding HTML to documentation?

HTML support within Markdown is limited.

See our [Markdown Documentation](https://meta.stoplight.io/docs/studio-demo/docs/markdown/basic-syntax.md) for more information.

## How do I allow Stoplight to access an internal Git provider?

All network traffic from Stoplight originates from a fixed IP address. This is done so that network administrators can allow Stoplight to access your internal Git or identity providers with minimal risk to your network.

The fixed IP address is: **35.226.194.249**

## What browsers does Stoplight support?

We aim to support the following browsers and minimum versions. 

|               | Chrome | Safari        | Firefox | Edge          |
| ------------- | ------ | ------------- | ------- | ------------- |
| Documentation | 68     | 12            | 60      | 18            |
| Platform      | 68     | 12            | 60      | Not Supported |
| Studio        | 75     | Not Supported | 68      | Not Supported |

Things may work outside of these browsers and these versions, but there might be unexpected problems as we won't be testing those environments.

If something is not working in a version listed here (or newer) please [contact support](mailto:support@stoplight.io).
