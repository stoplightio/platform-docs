# Using a Custom Domain

To setup a custom domain for your Stoplight workspace, follow the steps below:

![](../assets/images/custom_domain.png)

1. Select Workspace settings from the top-left drop-down
2. In Settings > Basics > Custom Domain
3. Enter the custom domain you would like to use. To complete the configuration
   process, you will need to create a CNAME DNS record for your domain that
   points to `ingress.stoplight.io`.

## Troubleshooting

### Cloudflare-hosted domains

If you are using [Cloudflare](https://cloudflare.com/), be sure to set your
CNAME record to "DNS Only" (signified by a grey cloud, and **not** an orange
cloud).

![](../assets/images/custom_domain_cloudflare.png)

You can read more about what this means in the CloudFlare documentation
[here](https://support.cloudflare.com/hc/en-us/articles/200169626-What-subdomains-are-appropriate-for-orange-gray-clouds-).

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
