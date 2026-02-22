# Deployment & Custom Domain Mapping

This document explains how to map custom domains (like `brainfeed.tech`) to the various hosting services used in this ecosystem.

## 1. Vercel (Next.js / React)

For projects hosted on Vercel (`industrial-portfolio-2026`, `autonomous-sec-agent-ops`, `cyber-intel-aggregator-service`):

1.  Go to the **Project Settings** in Vercel.
2.  Navigate to **Domains**.
3.  Add your custom domain (e.g., `brainfeed.tech` or `sec-agent.brainfeed.tech`).
4.  Update your DNS provider (e.g., Namecheap, Cloudflare) with the provided `A` or `CNAME` records:
    *   **A Record:** `@` -> `76.76.21.21`
    *   **CNAME Record:** `www` -> `cname.vercel-dns.com`

## 2. GitHub Pages (Static Sites)

For projects like `Pokedex`:

1.  Go to the **Settings** tab of the repository on GitHub.
2.  Navigate to **Pages** in the sidebar.
3.  Under **Custom domain**, enter your domain (e.g., `pokedex.brainfeed.tech`).
4.  Configure your DNS provider:
    *   **A Records:**
        *   `185.199.108.153`
        *   `185.199.109.153`
        *   `185.199.110.153`
        *   `185.199.111.153`
    *   **CNAME Record:** `pokedex` -> `<username>.github.io`

## 3. Automated SSL

Both Vercel and GitHub Pages provide automated SSL certificate provisioning via Let's Encrypt once the DNS records are verified.

---
Part of the [Industrial Portfolio 2026](https://github.com/Brainfeed-1996/industrial-portfolio-2026) documentation.
