# Using a Custom Domain
## Setting up a custom domain
1. Select Workspace settings
2. In Settings > Basics > Custom Domain
3. Enter the custom domain to be used 
  (Note: Add a CNAME record to the DNS that points to "ingress.stoplight.io".)

![](../assets/images/custom_domain.png)

## Troubleshooting

### The connection has timed out

If you see an error related to "The connection has timed out", this typically
means that a CAA DNS record is present on your domain, which is preventing the
TLS verification process from completing.

> To learn more about CAA records and what they are used for, see the Let's
> Encrypt documentation [here](https://letsencrypt.org/docs/caa/). You can
> perform a CAA lookup on your domain [here](https://dnslookup.online/caa.html)
> for reference.

To resolve this issue, use either option below:

- **RECOMMENDED** Add `letsencrypt.org` to the CAA record to allow Let's Encrypt
  to generate certificates for your domain.

- **NOT RECOMMENDED** Remove the CAA DNS record from your domain, which will
  allow any authority to generate certificates for the domain.

Once updated, try to navigate to your custom domain again to verify the issue
has been resolved.
