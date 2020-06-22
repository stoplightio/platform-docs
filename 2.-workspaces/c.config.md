---
tags: [Workspaces]
---

# Configure Projects

Seeing as your projects can contain all sorts of files, sometimes you might not want Stoplight to analyze specific files. For example, if a project is backed by a Git repo which also contains a bunch of developer-only internal Markdown files, you might not want those going on your public documentation, 

There is a `.stoplight.json` config file, which can help with that, using an `"exclude"` to blacklist certain files/folders.

There's also a `"formats"` keyword to instruments which files are supposed to be read and parsed as APIs, documentation, or other content. When you create an API in Studio, it can use this configuration to know where to put that file, so it's not just shoved into the root along with everything else.

![](../assets/images/create-api-with-config.gif)

## How it Works

The config file should go in the root of your project, and be named `.stoplight.json`. It can be regular JSON or [JSONC](https://github.com/microsoft/node-jsonc-parser) (i.e. JSON with comments, and trailing commas allowed).

Projects with no config file will act as though they had this config:

```json
{
  "formats": {
    "openapi": {
      "rootDir": "reference",
      "include": ["**"]
    },
    "markdown": {
      "rootDir": "docs",
      "include": ["**"]
    },
    "image": {
      "rootDir": "assets/images",
      "include": ["**"]
    },
    "json_schema": {
      "rootDir": "models",
      "include": ["**"]
    }
  }
}
```

Any files with the `openapi` and `json_schema` formats will go under the "APIs" panel, and any files with `markdown` or `images` formats will go under "Docs".

The funny-looking stars in the `"include"` are a [glob](https://en.wikipedia.org/wiki/Glob_(programming)) pattern, for finding files based on a pattern. More specifically, we're using an open-source library called [micromatch](https://github.com/micromatch/micromatch). 

## Reference

### `exclude`

Any file or directory matching the pattern listed in `exclude` won't be indexed by Stoplight.

> **Note:** There is a fairly large default list of excluded file paths for things like node modules and other common dependency management files, `.cache/`, `.git`, `log/`, `tmp/`, etc. This is done for performance reasons and will be made more observable and configurable in future versions.

### `formats`

- `rootDir` (required) - when `include` is unspecified, all files placed under `rootDir` are marked as included. Used by UI wizards in Studio as a default location for certain kinds of files.
- `include` (optional) - at least one pattern needs to match the `rootDir`.

## Example

Maybe a project has multiple APIs in a `apis` directory, some test files that should not be indexed, and some models in a `schemas` directory, which you also use for [contract testing](https://apisyouwonthate.com/blog/writing-documentation-via-contract-testing).

```
help/article.md
apis/petstore.openapi.yaml
apis/address.openapi.json
test/todos.openapi.yaml
schemas/user.json
.stoplight.json
```

To exclude the test files and make it clear which other files are which, the following `.stoplight.json` could be used:

```json
{
  "formats": {
    "openapi": {
      "rootDir": "apis"
    },
    "json_schema": {
      "rootDir": "schemas"
    },
    "markdown": {
      "rootDir": "help"
    },
  },
  "exclude": ["test"]
}
```
