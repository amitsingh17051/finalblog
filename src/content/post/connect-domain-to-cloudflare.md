---
title: "Connect godaddy domain to cloudflare"
description: "Connecting your GoDaddy domain to Cloudflare involves a few steps. Cloudflare free plan offers essential services like CDN and security features."
publishDate: "24 Jan 2024"
tags: ["Cloudflare", "DNS", "Domain"]
draft: false
---

## How to Connect GoDaddy to Cloudflare and Set Up Cloudflare Free Package Services

### 1. Sign up for Cloudflare:

- If you don't have a Cloudflare account, sign up for one at [Cloudflare](https://www.cloudflare.com/).

### 2. Add your website to Cloudflare:

- Once logged in, click on "Add a Site" in the Cloudflare dashboard.
- Enter your domain name and follow the instructions to scan your DNS records. Cloudflare will attempt to import your existing DNS settings.

### 3. Change Nameservers at GoDaddy:

- After adding your site on Cloudflare, it will provide you with new nameservers.
- Log in to your GoDaddy account and navigate to the domain management section.
- Update the nameservers to the ones provided by Cloudflare.

### 4. Adjust Cloudflare settings:

- Go back to the Cloudflare dashboard and explore the different settings.
- Ensure that the essential settings for your website are configured. This may include SSL/TLS settings, security levels, caching options, etc.
- Under the "SSL/TLS" tab, set the SSL option to "Flexible" for the free plan.

### 5. Check your DNS settings:

- Confirm that all necessary DNS records are correctly configured on Cloudflare. These might include A, CNAME, and MX records, among others.

### 6. Enable Cloudflare's Free Services:

- The free plan offers basic services like CDN and security features. You can configure these under the "Speed" and "Security" sections in the Cloudflare dashboard.
- Set up page rules, if needed, to fine-tune the behavior of Cloudflare for specific URLs.

### 7. Wait for DNS Propagation:

- Changes to DNS settings may take some time to propagate globally. Be patient, and once the changes have propagated, your website should be served through Cloudflare.

### 8. Verify:

- After DNS propagation, visit your website and ensure it's loading through Cloudflare. You can also check the Cloudflare dashboard for any issues or alerts.

Remember that specific steps may vary slightly based on updates to the Cloudflare interface or changes in GoDaddy's platform. Always refer to the latest documentation provided by both services for the most accurate instructions.
