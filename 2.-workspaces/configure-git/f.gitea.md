# Gitea

> This feature is available on the Stoplight **Pro** plan, and above

Configure your Gitea integration by following the instructions below:

**Gitea**

1. Register a new application via the (/user/settings/applications) section of the settings.
2. In the application form, enter a Name e.g `Stoplight Integration`, and set the Redirect URI as: `https://stoplight.io/oauth/callback`. Click **Submit**.

**Stoplight Workspace**

3. Navigate to the Integrations section in your Stoplight workspace settings. 
4. Click **Install/Configure** beside Gitea. 
5. Add the following information:
 - **Host URL**: This is the URL where your instance of Gitea is hosted.
 - **API URL**: This is the URL of the API of your instance of Gitea. This is usually: `{HostURL}/api/v1`
 - **Client ID**: You can find this as `Client ID` under the application settings for the newly created app. 
 - **Client Secret**: You can find this as `Secret` under the application settings for the newly created app. 
6. Click **Install**. 

If successful, [add projects](../b.adding-projects.md) to start working with projects from your Gitea instance.

If you receive an error verify the following and try again:

- Client ID and Client Secret are correct
- Host and API URL is correct

If connected behind a firewall verify the following:

Stoplight's IP addresses are added to your [allowlist](../e.whitelisting-ips.md) on port 443. 
