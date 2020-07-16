# GitHub Enterprise

> This feature is available on the **Pro** plan and above

Configure your GitHub Enterprise integration by following the instructions below:

**GitHub**

1. In the upper-right corner of any page, click your profile photo, then click Settings.
2. In the left sidebar, click Developer settings. Then, click OAuth Apps.
3. Click New OAuth App.
> If you haven't created an app before, this button will say, Register a new application.
4. In "Application name", type the name of your app. e.g `Stoplight Integration`. In "Homepage URL", type the full URL to your app's website. e.g.: `https//stoplight.io`
5. Set the Authorization callback URL as: `https://stoplight.io/oauth/callback`. Click **Register application**.

**Stoplight Workspace**

6. Navigate to the Integrations section in your Stoplight workspace settings. 
7. Click **Install/Configure** beside GitHub. Select **Customize integration settings**. 
8. Add the following information:
 - **Host URL**: This is the URL where your instance of GitHub Enterprise is hosted.
 - **API URL**: This is the URL of the API of your instance of GitHub Enterprise. This is usually: `api.{HostURL}`
 - **Client ID**: You can find this as `Client ID` under the OAuth Apps settings for the newly created app. 
 - **Client Secret**: You can find this as `Client Secret` under the OAuth consumers settings for the newly created app. 
9. Click **Install**. 

If successful, [add projects](../b.adding-projects.md) to start working with projects from your GitHub Enterprise instance.

If you receive an error verify the following and try again:

- Client ID and Client Secret are correct
- Host and API URL is correct

Read more about [creating a GitHub OAuth App](https://developer.github.com/apps/building-oauth-apps/creating-an-oauth-app/).

If connected behind a firewall verify the following:

Stoplight's IP addresses are added to your [allowlist](../h.allowlisting-ips.md) on port 443. 
