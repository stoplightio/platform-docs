# Bitbucket Server

> This feature is only available on the **Pro** plan and above.

Configure your Bitbucket Server integration by following the instructions below:

1. Navigate to the Integrations section in your Stoplight workspace settings. 
2. Click **Install/Configure** beside Bitbucket Server.
3. Add the following information:
 - **API URL**: This is the URL of the API of your instance of Bitbucket Server. This is usually: `{HostURL}/rest/api/1.0` where the HostURL is the URL where your instance of Bitbucket Server is hosted.
4. Click **Install**. 

If you receive an error verify the following and try again:

- API URL is correct

If connected behind a firewall verify the following:

Stoplight's IP addresses are added to your [allowlist](../../c.troubleshooting.md#how-do-i-allow-stoplight-to-access-an-internal-git-provider) on port 443. 
