# Review API Designs

When you're a solo developer working on an API design, the process is pretty simple:

1. Make some changes
2. They're great
3. Ship it

When multiple developers are working on the API, and when multiple teams are all making multiple APIs, quality control can suddenly feel more important.

## When to Review?

When creating a new API from scratch, the first step to design, before you even open up Studio, is interviewing potential consumers and finding out their needs. Getting as many involved as possible and aggregating results to make the most popular use cases as easy and efficient as possible will help you make a good API. 

Whatever designs, [mock-powered prototypes](d.setting-up-a-mock-server.md), or code-powered pilot/alpha APIs come from this can be reviewed. Much of this will happen outside of Stoplight, through Slack or your organizations general communication channels.

After an API has launched, any new functionality and changes can also be reviewed. These will feel very similar to code reviews.

Changes can be made at the same time as the code, then code and API description is reviewed in the same pull request at the same time, but that can lead to a lot of spam as API reviews trigger another round of code review, and vice versa. 

Instead, it can help to make the API description changes _before_ the code is written, then if the API description gets a thumbs up the code can be written to that existing contract.

## Who does Reviews?

If there are only two API developers, then maybe each developer checks the others.

If there are 1,000 API developers then maybe you need a dedicated team. These teams have many names:

- API Design Reviewers
- API Gatekeepers
- API Center of Excellence
- Architectural Committee

Whatever size an organization is, developers alone should not be handling all reviews. Getting clients involved with the changes that are coming, before they're unleashed on the API ecosystem, can help increase moral, reduce code churn, and generally keep everyone on the same page.

## What to Look Out For

**Are there breaking changes?**

API reviewers will want to look out for changes that: remove endpoints, rename a properties, change the data type of existing properties, remove enum values, or any other sort of breaking change.

**Does the terminology make sense?**

Is the term "account" being introduced to describe users, when other parts of the API ecosystem at your organization use it for "companies" or maybe even financial reasons? Is there maybe a better term that could be used?

**Is this consistent?**

API consumers generally don't enjoy guessing subtle differences between various APIs from the same organization, and they shouldn't need to. 

- If one API uses JSON:API and another uses Siren, maybe that's something to call out. 
- If one uses camelCase for properties and another uses snake_case, maybe that could be mentioned.

Spectral can help with a lot of this, allowing you to [create style guides for workspaces](../5.-governance/d.style-guides.md). This will catch a lot of trouble sooner, but humans can still check the results after for anything which doesn't have a Spectral rule.

**Is this easy to implement?**

Sometimes things are hard, but sometimes things are unnecessarily hard. If an API has been designed in a way that's just going to be a nightmare to implement, or involves making way too many HTTP calls to get a basic task done, this feedback can be made early on before more time and money is wasted.

## How does Design Review Work?

Most developers are used to changing to source code in version control systems via "pull requests", at which point various teammates or other folks will review the code. Seeing as Stoplight lets you continue to use your Git repository as a source of truth, this same process can be used for OpenAPI and JSON Schema reviews too.

### 1. Open a Project in Studio

Whether you're [creating a new project](../2.-workspaces/a.creating-a-workspace.md) or changing an existing one, pick a project to open in Studio.

### 2. Create a new Branch

A lot of Git repositories (especially those on GitHub) are configured to use [protected branches](https://help.github.com/en/github/administering-a-repository/about-protected-branches), which means pushing to master is not possible. Maybe you can push to master, maybe not, but if you'd like other people to review your work, it is best to create a branch to keep the changes out of master until they've been reviewed.

![New branch in Studio](../assets/images/new-branch-studio.gif)

Read more about [creating and switching branches](https://meta.stoplight.io/docs/studio/docs/Basics/04-common-git-tasks.md#switching-branches).

### 3. Make Changes, Commit, & Push

When you're done making changes, [commit them, then push](https://meta.stoplight.io/docs/studio/docs/Basics/04-common-git-tasks.md#committing-changes) the branch to the remote repository. 

### 4. Open a Pull Request

How you create a pull request depends on where the project's repository is hosted:

- **BitBucket:** [Create a Pull Request](https://www.atlassian.com/git/tutorials/making-a-pull-request)
- **Gitea:** [Create a Pull Request](https://docs.gitea.io/en-us/pull-request/)
- **GitHub:** [Create a Pull Request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)
- **GitLab:** [Create a Merge Request](https://docs.gitlab.com/ee/user/project/merge_requests/)

### 5. Link to Branch Documentation

If [webhooks are enabled](../2.-workspaces/g.automating-publishing.md) the branch should appear in the documentation almost immediately. The branch name will appear in the versions dropdown, probably under "Unpublished Branches".

![The version dropdown in documentation showing various unpublished branches](../assets/images/docs-selecting-branches.png)

_Read more about [branch management](../2.-workspaces/h.branch-management.md) if you would like to know the different between published and unpublished branches, and the versions dropdown._

Selecting your new branch from the Versions dropdown should take you to a URL like this:

```
https://{workspace}.stoplight.io/docs/{project}/branches/{branch}
```

Copy and paste that link into the pull request, so API reviewers can eyeball the rendered documentation instead of having to read a bunch of YAML.

### 6. Review & Merge

Reviewers can then give feedback on the pull request, you go back to step 3 to make changes, then push, and when the changes are approved you're done! Merge that pull request.
