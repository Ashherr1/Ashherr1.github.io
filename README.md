# tesla-fleet-key

Hosts the **public** key for my Home Assistant Tesla Fleet developer app via GitHub Pages.

Tesla fetches it from:

    https://<domain>/.well-known/appspecific/com.tesla.3p.public-key.pem

- Home Assistant (`192.168.40.9`) generates the private key itself at `config/tesla_fleet.key`, and it stays there.
- The Tesla Fleet config flow shows the matching public key. That value goes in
  `.well-known/appspecific/com.tesla.3p.public-key.pem`.
- `.nojekyll` is required. Without it, Pages won't serve the `.well-known` folder.
- `CNAME` holds the custom domain. Its DNS needs a `CNAME` record pointing to `<user>.github.io`, and
  "Enforce HTTPS" must be on, because Tesla requires valid TLS.

**Never commit a private key here.**
