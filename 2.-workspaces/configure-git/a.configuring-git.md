# Overview

Stoplight can connect with popular Git Providers hosted publically or on your servers (even if it's protected by a firewall), letting you work directly with [projects](../b.adding-projects.md) in public or private repos. 

## Git Provider Support

We support the following Git providers.

- Bitbucket Cloud
- Bitbucket Server
- GitHub
- GitLab
- Gitea
- Azure Devops (*Coming Soon*)

If you don't see the Git Provider you're looking for, take a look at our [roadmap](https://roadmap.stoplight.io/) to keep an eye on what's coming next. You can also use [Stoplight CLI](../g.working-with-local-projects.md) to push projects to Stoplight Platform.

## Configure Cloud Git Providers

Cloud-hosted Git providers are configured out of the box in Stoplight. The following cloud Git providers are supported:

- Bitbucket Cloud
- GitHub
- GitLab

1. Install your desired Git provider from the integrations section in your workspace settings. 

![Install integrations from Workspace Settings > Integrations](../../assets/images/git-integrations.png)

2. Select **Use Default Configuration** and click **Install**. 

If you have a self-hosted deployment or are looking for custom integration settings, use the guides below.

## Configure Self Hosted Git Providers

> If your self hosted Git provider is behind a firewall, please [add our IPs to your allowlist](../e.whitelisting-ips.md) on port 443 over HTTPS. 

> This feature is available on the **Pro** plan and above

Configure your Git Provider using the guides below:

- [Bitbucket Cloud](b.bitbucket-cloud.md)
- [Bitbucket Server](c.bitbucket-server.md)
- [GitHub Enterprise](d.github-enterprise.md)
- [GitLab](e.gitlab.md)
- [Gitea](f.gitea.md)
