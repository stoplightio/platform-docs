# GitLab

> This feature is available on the Stoplight **Pro** plan, and above

Configure your GitLab integration by following the instructions below:

**GitLab**

1. To add a new application via your profile, navigate to **Profile Settings > Applications** and select **New Application**.
2. In the application form, enter a Name e.g `Stoplight Integration`, and set the Redirect URI as: `https://stoplight.io/oauth/callback`. Click **Submit**.

**Stoplight Workspace**

3. Navigate to the Integrations section in your Stoplight workspace settings. 
4. Click **Install/Configure** beside GitLab. Select **Customize integration settings**. 
5. Add the following information:
 - **Host URL**: This is the URL where your instance of GitLab is hosted.
 - **API URL**: This is the URL of the API of your instance of GitLab. This is usually: `{HostURL}/api/v4`
 - **Client ID:** You can find this as `Application ID` under the application settings for the newly created app. 
 - **Client Secret**: You can find this as `Secret` under the application settings for the newly created app. 
6. Click **Install**. 

If successful, [add projects](../b.adding-projects.md) to start working with projects from your GitLab instance.

If you receive an error verify the following and try again:

- Client ID and Client Secret are correct
- Host and API URL is correct

Read more about [creating a GitLab OAuth App](https://docs.gitlab.com/ee/integration/oauth_provider.html#adding-an-application-through-the-profile).

If connected behind a firewall verify the following:

Stoplight's IP addresses are added to your [allowlist](../e.whitelisting-ips.md) on port 443. 
