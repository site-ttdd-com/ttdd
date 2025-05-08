# 🚀 TTDD Static Site Deployment Guide

This document outlines the steps to deploy the TTDD.com static site, built with Next.js and hosted via GitHub Pages.

---

## ⚙️ 1. Configure `next.config.ts`

Ensure your `next.config.ts` has the correct settings for root-domain deployment:

\`\`\`ts
const nextConfig: NextConfig = {
  output: 'export',
  basePath: '',
  assetPrefix: '',
  trailingSlash: true,
  images: { unoptimized: true },
  eslint: { ignoreDuringBuilds: true },
  typescript: { ignoreBuildErrors: true },
}
export default nextConfig;
\`\`\`

---

## 🛠️ 2. Build the Site

Run the build:

\`\`\`bash
pnpm build
\`\`\`

This will generate the static site in the `/out` directory.

---

## 🚀 3. Prepare for Deployment

Before deploying, make sure the following files are present in `/out`:

- `index.html`
- `_next/` folder (with CSS, JS, fonts, media, etc.)
- `.nojekyll` (to prevent GitHub from ignoring `_next`)
- `CNAME` file with:
  \`\`\`
  www.ttdd.com
  \`\`\`

Create `.nojekyll` if missing:

\`\`\`bash
touch out/.nojekyll
\`\`\`

---

## ⬆️ 4. Deploy to GitHub Pages

1. Copy the **contents of `/out`** (not the folder itself) to the root of your GitHub Pages repository.
2. Then:

\`\`\`bash
git add .
git commit -m "Deploy static site"
git push
\`\`\`

---

## 🌐 5. GitHub Pages & DNS Setup

### GitHub Pages Settings:
- Source: `main` branch, `/ (root)`
- Custom domain: `www.ttdd.com`
- Enforce HTTPS: ✅

### DNS Records (via domain registrar):

\`\`\`
| Type  | Name | Value                    |
|-------|------|--------------------------|
| A     | @    | 185.199.108.153          |
| A     | @    | 185.199.109.153          |
| A     | @    | 185.199.110.153          |
| A     | @    | 185.199.111.153          |
| CNAME | www  | site-ttdd-com.github.io  |
\`\`\`

---

## ✅ 6. Post-Deploy Checks

- [ ] Site loads at https://www.ttdd.com
- [ ] Fonts, CSS, and JS load (check dev tools console)
- [ ] HTTPS is enforced
- [ ] No 404s for `_next/static/*` resources

---

## 🔁 Optional: GitHub Actions

You can automate deployment using a GitHub Actions workflow.

Ask ChatGPT for a sample `.github/workflows/pages.yml` file if you'd like to set that up.

