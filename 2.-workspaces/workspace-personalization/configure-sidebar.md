# Configure Sidebar


The sidebar on your documentation is customizable, and can be optimized for better navigation. In this guide learn how you can rearrange your artifacts for a seamless experience. 

# What is the Sidebar?

Through out your Stoplight workspace, there runs a bar on the left side of your screen, which we call the **sidebar**. The colors sidebar can be adjusted to match the look the feel of your brand, but more importantly, it can be customized to rearrange elements for better navigation on your documentation.  

The [default structure](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#the-default-structure) of this sidebar loosely follows the filesystem of your project, with a few exceptions for APIs and models. 

> **👉 Note:** Find out how default file structures look on Stoplight: **Stoplight Directory Structure** 

You can [customize the appearance](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#customizing-the-sidebar) of this sidebar using a **Table of Contents** file (`toc.json`), which supports:

- Customizing the order of files in the sidebar
- Overriding the title of a file in the sidebar
- Selectively exposing files in the sidebar, allowing you to hide items by not including them in your Table of Contents file

![Configure Sidebar](../../assets/images/CS.png)

### Before you get started**:**

There are a few limitations with this functionality that you need to keep in mind before you get started. 

1. **You can only reorder articles, APIs, and model files.** Endpoints and internal models will follow the [default structure](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#the-default-structure) outlined below. [(roadmap)](https://roadmap.stoplight.io/c/110-custom-ordering-for-endpoints-and-models)
2. **The `toc.json` file must be written by hand.** [(roadmap)](https://roadmap.stoplight.io/c/112-table-of-contents-editor)
3. **Renaming a file does not automatically update the `toc.json`.** You'll need to remember to update your TOC whenever a file is renamed. Otherwise your project sidebar might contain broken links. [(roadmap)](https://roadmap.stoplight.io/c/96-automatically-rewrite-references-and-links-on-filename-change)
4. **Renaming a file does not automatically redirect to the new docs url**. This means changing a filename might result in broken links. [(roadmap)](https://roadmap.stoplight.io/c/68-automatic-redirects)

## Table of Contents File

To configure the sidebar, you first need to understand the **Table of Contents** `**toc.json**` file. There are three types of entities in the Table of Contents:

- **Dividers**
- **Groups**
- **Items**

![Configure Sidebar](../../assets/images/CS1.png)

### **Dividers:**

Dividers are bold, non-clickable items that signify the start of a section of content within the sidebar.

### **Groups:**

Groups are non-linkable, collabsible items containing items and other groups that all relate to the same subject matter. Dividers cannot be nested within a group.

### **Items:**

Items are links to articles, APIs, and model files located within the project directory or external links to content outside of the documentation.

## **Default Structure**

When the `toc.json` file is not present, the default structure is organized based on a few factors, such as the file type, but primarily follows the same alphanumeric ordering of the filesystem.

### **Articles**

Markdown articles come first in the table of contents and are ordered alphabetically by their file path. The first directory is represented as a [divider](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#dividers) and any directories after appear as [groups](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#groups).

There are a few exceptions. If a "docs" folder exists, it is flattened and not represented in the table of contents. Any articles located in the root of the project are sorted to the top.

**Tip:** If a `README.md` file exists, it is put in the first position.

### **APIs**

Next in the list below articles are your APIs. Each API's title is represented as a [divider](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#dividers) followed by an item titled "Overview". The overview item contains the API's description, contact, licensing, servers and global security.

All of the API endpoints and models are nested inside [groups](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#groups) titled after their first tag. Any without tags are placed into a group titled "other". If none of your endpoints or models contain tags, they are placed into groups titled "Endpoints" and "Models" respectively.

### **Models**

Finally at the bottom of the table of contents are JSON Schema model files, sorted alphabetically under a [divider](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#dividers) titled "Models".

## **Custom Structure**

If you want to customize the organization of your project's content structure, you can do that by  creating a custom table of contents file. To get started, create a `toc.json` file in your project's **root directory**.

### **Rules**

The `toc.json` file should start off with an empty `items` array where you will define your content structure using [dividers](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#dividers), [groups](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#groups) and [items](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md#items).

toc.json

```
{
  "items": []
}
```

> **👉 Note:**
Each entity should have a `type` and a `title` property.
>- Items should also have a `uri` property that either points to a file somewhere within the project or an external link to another website.
>- Groups should have an `items` property allowing you to further nest more items and groups.

> **👉 Tip**: The easiest way to get a file's URI in Studio is to click the `...` button next to the file, click the "copy path" menu item then paste the contents. 

**Example**

![https://raw.github.com/stoplightio/platform-docs/main/assets/images/studio-copy-path.gif](https://raw.github.com/stoplightio/platform-docs/main/assets/images/studio-copy-path.gif)

Here is an example to demonstrate the format of the `toc.json` file.

toc.json

```json
{
  "items": [
    {
      "type": "divider",
      "title": "Divider"
    },
    {
      "type": "item",
      "title": "Item",
      "uri": "docs/table-of-contents.md"
    },
    {
      "type": "group",
      "title": "Group",
      "items": [
        {
          "type": "item",
          "title": "Nested Item",
          "uri": "docs/nested-item.md"
        }
      ]
    },
    {
      "type": "item",
      "title": "External Link",
      "uri": "https://stoplight.io"
    }
  ]
}
```

The above `toc.json` file displays the following structure in the docs sidebar.

![https://raw.github.com/stoplightio/platform-docs/main/assets/images/custom-toc-example.png](https://raw.github.com/stoplightio/platform-docs/main/assets/images/custom-toc-example.png)

## Adding Table of Contents file to your project

Adding a table of contents `toc.json` to your project is very easy. To do that: 

1. From your dashboard, navigate to your project and click **edit** to open **Studio.** 
2. On the studio, click the + **add** item button on top left of the page. 
3. From the dropdown that opens, select **Table of Contents**. 

![Configure Sidebar](../../assets/images/CS5.png)

4. Click **Generate default content for a** default structure**,** or ****add something of your own, ****for a **custom structure.** 

5. The `toc.json` file will sit in the root directory of your project. 

5. Once done, **push** changes to Git. 

**You now know how to configure your sidebar. Ensure you have the best navigation for great developer experience. ⚡️**

## **What's next?**

Now that you know how to configure these analytics, read on to learn the next best steps: 

- **[Configuring analytics](../configuring-analytics.md)**
- **[Sharing Documentation](../../1.-quickstarts/share-documentation-quickstart.md)**