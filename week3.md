## Learning journal entry — Week 3 (Prac 3)

**Title:** WordPress CMS, public hosting, and group formation

### What I did this week

- Installed **WordPress** (wordpress.org — self-hosted, not wordpress.com) for my **Vegely** startup site.
- Set up a **local** copy using **LocalWP** on Windows at `http://vegely.local` for development and Prac 4 demos.
- Deployed a **public** WordPress site on **InfinityFree** at **[https://vegely.site.je/wp/](https://vegely.site.je/wp/)** (subdomain `vegely.site.je`, WordPress installed in the `/wp/` folder via Softaculous / Script Installer).
- Reused content from my Week 1 static HTML site and Week 2 Joomla site: Home, Menu, About, Contact pages, Singapore pricing, team bios, and food images.
- Configured the public site with the **Twenty Twenty-Five** theme, static homepage (**Home**), and a main navigation menu.
- Uploaded brand images to `wp-content/uploads/vegely/` (hero, dishes, team folders) via InfinityFree File Manager.
- Kept my **Joomla** assignment site on **AwardSpace** at `http://vegely.atwebpages.com/` — separate from WordPress.

### Hosting decisions

| Site | Platform | URL | CMS |
|------|----------|-----|-----|
| Assignment (Week 2) | AwardSpace | vegely.atwebpages.com | Joomla 5 |
| Prac 3 (public) | InfinityFree | vegely.site.je/wp/ | WordPress |
| Prac 4 (local) | LocalWP | vegely.local | WordPress |

AwardSpace free hosting only allows **one MySQL database**, which Joomla already uses. I could not install a second WordPress instance there without removing Joomla or sharing the database manually. I moved public WordPress to **InfinityFree**, which provides its own database and one-click WordPress install.

### WordPress vs Joomla — reflections

| Aspect | Joomla (AwardSpace) | WordPress (Local + InfinityFree) |
|--------|---------------------|----------------------------------|
| Installation | Zacky Joomla installer | LocalWP (local) + Script Installer (InfinityFree) |
| Content editing | Articles, categories | Pages + block editor |
| Extensions | Joomla extensions | WordPress plugins |
| Best for | Structured CMS, template overrides | Fast marketing sites, large plugin ecosystem |

Both are **PHP + MySQL** CMSs. WordPress felt quicker for rebuilding my Vegely pages using the block editor. Joomla gave more control over template structure (Cassiopeia overrides, `user.css`) but took longer to customise.

### Challenges and how I solved them

| Problem | Solution |
|---------|----------|
| AwardSpace: "need at least one database" when installing WordPress | Used InfinityFree for public WordPress; kept Joomla on AwardSpace |
| Could not log in to WordPress after Softaculous install | Skipped Softaculous onboarding wizard; used wp-admin directly; reset password via hosting tools if needed |
| InfinityFree DNS slow / connection timeout on first day | Waited for propagation; used `http://` instead of `https://` initially |
| WordPress installed in `/wp/` subfolder, root showed placeholder page | Used `vegely.site.je/wp/` as the public URL; documented in submission |
| Zip extract showed nothing in File Manager | Used **Upload & Unzip** per folder, or moved extracted `vegely/` folder to `uploads/vegely/` |
| Images one level too deep (`uploads/vegely-images/vegely/`) | Moved inner `vegely` folder up to `uploads/vegely/` |
| `vegely.local` connection refused | Started the site in **LocalWP** app (site must be **Running**) |


### Plugins to explore

- **Contact Form 7** — contact page form
- **Yoast SEO** or **Rank Math** — meta descriptions and SEO basics
- (Optional) security or cache plugin

### What I learned

- WordPress.org self-hosted is different from wordpress.com (course requirement).
- A CMS site needs **PHP + MySQL + a web server** — static HTML files alone are not enough for Prac 3/4.
- Free hosting has real limits (database count, DNS delay, file manager quirks).
- Local development (LocalWP) and production (InfinityFree) are separate environments — content and files must be migrated or recreated.
- Reusing startup content across static HTML → Joomla → WordPress saved time; the prac focus was learning the CMS, not redesigning from scratch.

### Links

- **Public WordPress (Prac 3):** [https://vegely.site.je/wp/](https://vegely.site.je/wp/)
- **Local WordPress (Prac 4):** http://vegely.local
- **Joomla (Week 2):** http://vegely.atwebpages.com/
