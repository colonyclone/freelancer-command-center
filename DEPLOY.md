# Deploy Landing Page to GitHub Pages

## Steps to go live (free hosting, custom domain optional)

### 1. Create a GitHub repo
  git init
  git add .
  git commit -m "Initial landing page"

  Go to github.com → New repository
  Name it: freelancer-command-center
  Make it Public (required for free GitHub Pages)
  Don't initialize with README

### 2. Push your code
  git remote add origin https://github.com/YOUR_USERNAME/freelancer-command-center.git
  git branch -M main
  git push -u origin main

### 3. Enable GitHub Pages
  Go to repo → Settings → Pages
  Source: Deploy from branch
  Branch: main / (root)
  Click Save

  Your site goes live at:
  https://YOUR_USERNAME.github.io/freelancer-command-center/

  Takes 1-3 minutes to deploy.

### 4. Update placeholders in index.html
  Replace YOUR_GUMROAD_LINK_HERE with your actual Gumroad product URL
  Replace YOUR_EMAIL_HERE with your contact email
  Replace YOUR_USERNAME with your GitHub username in robots.txt and sitemap.xml

### 5. Optional: Custom domain
  Buy a domain (Namecheap ~$10/yr): e.g. freelancercommandcenter.com
  In GitHub Pages settings → Custom domain → enter your domain
  Add CNAME record at your DNS provider pointing to YOUR_USERNAME.github.io
  Check "Enforce HTTPS"

---

## Sharing the landing page

Once live, share this URL everywhere instead of the raw Gumroad link.
The landing page:
  - Builds trust before the sale
  - Works for SEO (Google indexes it)
  - Lets you collect emails even if someone doesn't buy today
  - Gives you a real web presence

Post the URL on:
  - Reddit (r/Notion, r/freelance, r/productivity)
  - Twitter/X bio and launch thread
  - Pinterest (screenshot → pin → link to your page)
  - Your email signature
  - Any freelance communities you're in (Slack, Discord, Facebook groups)
