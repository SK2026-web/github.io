# Evoke The Mind Counselling — static site

A plain HTML/CSS rebuild of etmcounselling.com.au, with the same 6 pages and content, ready to host on GitHub Pages instead of WordPress. No WordPress code is used anywhere — every file here was written from scratch.

## Files

- `index.html` — Home
- `about.html` — About Us
- `our-services.html` — Our Services
- `first-session.html` — What can I expect at the first session?
- `pricing.html` — Our Pricing
- `contact.html` — Contact Us
- `css/style.css` — all styling
- `images/` — put your photos here (see `IMAGE-GUIDE.md`)

## 1. Add your images

Follow `IMAGE-GUIDE.md` first — the pages will look broken until the images are in place.

## 2. Put it on GitHub

1. Go to https://github.com and sign in (or create a free account).
2. Click the **+** in the top right → **New repository**.
3. Name it something like `etm-counselling-site`. Keep it **Public** (required for free GitHub Pages). Click **Create repository**.
4. On the new repo page, click **uploading an existing file**.
5. Drag in all the files and folders from this project (`index.html`, `about.html`, `our-services.html`, `first-session.html`, `pricing.html`, `contact.html`, the `css` folder, and the `images` folder with your photos in it).
6. Click **Commit changes**.

## 3. Turn on GitHub Pages

1. In the repository, go to **Settings** → **Pages** (left sidebar).
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Under **Branch**, choose `main` and folder `/ (root)`, then **Save**.
4. Wait a minute, then refresh — GitHub will show a link like `https://yourusername.github.io/etm-counselling-site/`. That's your live site.

## 4. Point etmcounselling.com.au at it (optional)

If you want to keep the same domain name instead of the github.io address:
1. In **Settings → Pages**, enter `etmcounselling.com.au` under **Custom domain** and save. This creates a `CNAME` file in the repo automatically.
2. Go to wherever the domain is registered (check your WordPress/hosting account, or GoDaddy, VentraIP, Crazy Domains, etc.) and update its DNS records to point to GitHub Pages. GitHub's own instructions are the most reliable for this step: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
3. This is the one part I'd double check with your domain registrar's support if you're not sure — getting DNS wrong can temporarily take the site offline, and it can take a few hours to take effect either way.

## About the contact form

GitHub Pages only serves static files — it can't run the server-side code needed to email you when someone submits the contact form. I've wired the form up to **Formspree** (a free service made for exactly this):

1. Go to https://formspree.io and create a free account.
2. Create a new form with `etmcounselling@outlook.com` as the recipient.
3. Formspree will give you a form ID. Open `contact.html`, find this line:
   ```
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
   and replace `YOUR_FORM_ID` with the ID Formspree gives you.

Until that's done, the form will display but won't send anything — visitors can always still reach out via the email and phone links on the same page, which work immediately.

## 5. Getting found on Google (SEO)

I've added the on-page groundwork already: page titles and descriptions written around what people actually search for ("counselling Mornington Peninsula" etc.), a structured-data block so Google understands this is a local counselling business, a `sitemap.xml`, and a `robots.txt`. There's one required step and a couple of genuinely high-impact ones outside the code.

### Required: swap the placeholder URL

Every file uses `YOUR-USERNAME` as a placeholder for your GitHub username, since it didn't exist yet when I built this. Once you've created your GitHub account and repository, find-and-replace `YOUR-USERNAME` with your actual username in these files:

- `index.html` (appears twice — once in the meta tags, once in the structured data block)
- `about.html`, `our-services.html`, `first-session.html`, `pricing.html`, `contact.html` (once each)
- `robots.txt`
- `sitemap.xml`

If you're comfortable in a text editor, "Find in files" / "Find and Replace" for `YOUR-USERNAME` → `yourrealusername` across the whole folder is the fastest way. Otherwise send me your username once it exists and I'll do the swap for you.

**If you ever move to a custom domain** (etmcounselling.com.au) instead of the github.io address, the same placeholder needs updating to the real domain instead — just let me know and I'll handle it.

### The two things that matter more than code

On-page SEO (what's in this repo) helps Google understand and trust the *content*. But for a local service business, these two things typically matter more for actually ranking:

1. **Google Business Profile** — create a free listing at https://business.google.com with your business name, address area, phone, and hours. This is usually the single biggest factor in whether you show up when someone searches "counsellor near me" or "counselling Mornington Peninsula" — it's what populates the map pack at the top of Google results.
2. **Backlinks** — other real websites linking to yours (a directory listing, a mention from a local health network, your own social media profiles linking to the site) signal trust to Google. A brand-new site with no other site linking to it takes time to rank, regardless of how well-built the code is.

It's also worth submitting your sitemap to **Google Search Console** (https://search.google.com/search-console, free) once the site is live — it tells Google the site exists and lets you see how it's performing in search over time.

