---
tags: [Governance]
---

## Organize Projects

Who controls what projects, how many APIs go in a repo, etc. are all decisions that need to be made within your organization. Stoplight has no bias towards a "monorepo" or a "multirepo" approach, it supports either. 

If you are using a "monorepo" approach, you might have one project, with a directory for each API, and contain the source code and API description inside that directory.

If you are using a "multirepo" approach, you might have one project for each API, and contain the source code and API description inside each project in any directory structure you like.

You could use a mixture of both, where multiple repositories exist, but there are a couple of APIs in there. Maybe one project known as the "Locations Service" has a "Public API" and an "Admin API" for managing it.
