# tesla-fleet-key

Hosts the **public** key for my Home Assistant Tesla Fleet developer app via GitHub Pages.

Tesla fetches it from:

    https://ashherr1.github.io/.well-known/appspecific/com.tesla.3p.public-key.pem

- Home Assistant (`192.168.40.9`) generates the private key itself at `config/tesla_fleet.key`, and it stays there.
- The Tesla Fleet config flow shows the matching public key. That value goes in
  `.well-known/appspecific/com.tesla.3p.public-key.pem`.
- `.nojekyll` is required. Without it, Pages won't serve the `.well-known` folder.
- The domain is `ashherr1.github.io` itself (this is the user-site repo), so no DNS or `CNAME` is needed.

**Never commit a private key here.**
