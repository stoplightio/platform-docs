# Using a Custom Domain

## Troubleshooting

### The connection has timed out

If you see an error related to "The connection has timed out", this typically
means that a CAA DNS record is present on your domain, which is preventing the
TLS verification process from completing.

> To learn more about CAA records and what they are used for, see the Let's
> Encrypt documentation [here](https://letsencrypt.org/docs/caa/).

To resolve this issue, use either option below:

- **RECOMMENDED** Add `letsencrypt.org` to the CAA record to allow Let's Encrypt
  to generate certificates for your domain.

- **NOT RECOMMENDED** Remove the CAA DNS record from your domain, which will
  allow any authority to generate certificates for the domain.

Once updated, try to navigate to your custom domain again to verify the issue
has been resolved.
