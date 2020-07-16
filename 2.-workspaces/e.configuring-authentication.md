# Single Sign-On

Stoplight can connect with popular auth providers to simplify your authentication flows. 

## Auth Provider Support

We support the following Auth providers currently.

- LDAP
- SAML
- Bitbucket Cloud
- Bitbucket Server
- GitHub
- GitLab
- Gitea
- Azure Devops (*Coming Soon*)

To configure popular Git providers as auth providers follow [this guide](configure-git/a.configuring-git.md).

## Configure LDAP

> This feature is available on the Stoplight **Pro** plan, and above

You can use a Lightweight Directory Access Protocol (LDAP) authentication server to authenticate users with Stoplight. LDAP is an open-standard protocol for use with online directory services.

1. Navigate to the Integrations section in your Stoplight workspace settings. 
2. Click **Install/Configure** beside LDAP. 
3. Provide the following information:
 - **URL**: The LDAP host, e.g. **ldap://ldap.example.com**. If the hostname is behind a firewall, you may need to [add our IPs to your allowlist](e.whitelisting-ips.md).
 - **Bind DN**: The LDAP user that performs user lookups to authenticate other users when they sign in. This is typically a service account created specifically for third-party integrations. Use a fully qualified name, such as **cn=Administrator,cn=Users,dc=Example,dc=com**.
 - **Bind Credentials**: The password for the domain search user.
 - **Search Base**: The fully qualified Distinguished Name (DN) of an LDAP subtree you want to search for users and groups. You can add as many as you like; however, each group must be defined in the same domain base as the users that belong to it. e.g. **dc=Example,dc=com**.
 - **Search Filter**: Filters can be used to restrict the numbers of users or groups that are permitted to access an application.  In essence, the filter limits what part of the LDAP tree the application syncs from.  Read more about writing filters [here.](https://confluence.atlassian.com/kb/how-to-write-ldap-search-filters-792496933.html)
4. Click **Install**.


## Configure SAML

> This feature is available on the Stoplight **Pro** plan, and above

Organizations that need enhanced security requirements can configure SAML SSO allowing you to authenticate users with Stoplight. Security Assertion Markup Language (SAML) is a security standard for logging into applications. 

1. Navigate to the Integrations section in your Stoplight workspace settings. 
2. Click **Install/Configure** beside SAML. 
3. Provide the following information:
 - **Entry Point**: HTTPS endpoint of your IdP for single sign-on requests. This value is available in your IdP configuration. e.g. <!-- markdown-link-check-disable --> https://www.yourcompany.com/saml <!-- markdown-link-check-enable-->. If the entry point is behind a firewall, you may need to [add our IPs to your allowlist](e.whitelisting-ips.md).
 - **Identifier Format** 
 - **Identity Provider Public Certificate**: The authentication certificate issued by your identity provider. PEM-encoded X.509, 'BEGIN/END CERTIFICATE' lines should be stripped out and the certificate should be provided on a single line.
 - **Issuer**: Set the value here in your SAML server.
 - **Callback URL**: Set `https://{workspace-name}.stoplight.io/oauth/callback` as callback URL on your SAML server.
4. Click **Install**.
