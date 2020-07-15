# Bitbucket Cloud

Configure your Bitbucket Cloud integration by following the instructions below:

**Bitbucket Cloud**

1. From your profile avatar in the bottom left, click on the workspace in the Recent workspaces list or click All workspaces to open an entire list from which to choose.
2. Click Settings on the left sidebar to open the Workspace settings.
3. Click OAuth consumers under Apps and features on the left navigation, then click **Add consumer**.
4. Give the consumer a name e.g `Stoplight Integration`
5. Set the callback URL as `https://stoplight.io/oauth/callback`
6. Give the desired permissions to the consumer. The minimum you'd require is: `Account - Read`, `Repository - Admin`, `Repository - Write`, `Webhooks - Read and Write`. Click **Save**

**Stoplight Workspace**

7. Navigate to the Integrations section in your Stoplight workspace settings. 
8. Click **Install/Configure** beside Bitbucket Cloud. Select **Customize integration settings**. 
9. Add the following information:
 - **Host URL**: This is the URL where your instance of Bitbucket Cloud is hosted.
 - **API URL**: This is the URL of the API of your instance of Bitbucket Cloud. This is usually: `api.{HostURL}/2.0`
 - **Client ID**: You can find this as `Key` under the OAuth consumers settings for the newly created consumer. 
 - **Client Secret**: You can find this as `Secret` under the OAuth consumers' settings for the newly created consumer. 
10. Click **Install**. 

If successful, [add projects](../b.adding-projects.md) to start working with projects from your Bitbucket Cloud instance.

If you receive an error verify the following and try again:

- Client ID and Client Secret are correct
- Host and API URL is correct

Read more about [creating a BitBucket OAuth consumer](https://support.atlassian.com/bitbucket-cloud/docs/integrate-another-application-through-oauth/).

If connected behind a firewall verify the following:

Stoplight's IP addresses are added to your [allowlist](../e.whitelisting-ips.md) on port 443. 

