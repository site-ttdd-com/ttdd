README.txt

Project: TTDD Website
=====================

Overview:
---------
This repository hosts the source code for the TTDD website, a static site deployed using GitHub Pages. 
The live site is available at:

- Primary URL: https://www.ttdd.com
- GitHub Pages fallback: https://site-ttdd-com.github.io/ttdd/

Deployment:
-----------
The site is automatically deployed from the `main` branch using GitHub Pages.
The content is served from the root (`/`) of the repository.

Custom Domain Setup:
--------------------
This site uses a custom domain (www.ttdd.com). DNS is configured as follows:

1. CNAME Record:
   - Type: CNAME
   - Name: www
   - Value: site-ttdd-com.github.io

2. A Records (for root domain ttdd.com):
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153

Additionally, the repository includes a `CNAME` file with the following content:
   www.ttdd.com

Important Notes:
----------------
- GitHub Pages automatically builds and deploys the site on every commit to the `main` branch.
- Ensure DNS records are correctly set to maintain domain connection and HTTPS support.
- The site should use HTTPS (GitHub will auto-issue a certificate once DNS is verified).

Repository Structure:
---------------------
/               → Root folder with index.html and other static assets
/CNAME          → File declaring the custom domain
/README.txt     → Project information (this file)

Author & Maintainer:
--------------------
This project is maintained by the TTDD team.

