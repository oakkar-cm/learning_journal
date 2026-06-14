## Learning journal entry — Week 4 (Prac 4)

**Title:** Local development environment and deployment planning

### What I did this week

- Ran my **Vegely WordPress** site locally using **LocalWP** on Windows 10.
- Demonstrated a **dynamic site with a database** on localhost (`http://vegely.local`) — required for Prac 4.
- Continued work on the public WordPress site at **[https://vegely.site.je/wp/](https://vegely.site.je/wp/)** (InfinityFree) with pages, images, and navigation.
- Compared **local** vs **hosted** environments and researched options for deploying local changes to production.

### Local development stack

| Component | Details |
|-----------|---------|
| Tool | LocalWP (by WP Engine) |
| Web server | nginx (bundled by Local) |
| PHP | Bundled with Local site |
| Database | MySQL — database name `local` |
| Site URL | http://vegely.local |
| WordPress | 7.x |
| Project files | `C:\Users\Admin\Local Sites\vegely\app\public\` |
| Theme | Twenty Twenty-Five |

### What "dynamic site + database" means

Unlike my Week 1 static HTML Vegely site (files opened directly in a browser), WordPress stores content in **MySQL tables** (`wp_posts`, `wp_options`, `wp_users`, etc.). When I visit `http://vegely.local`, **nginx** passes the request to **PHP**, WordPress loads, queries the database, and generates HTML on each request. That makes it a **dynamic** CMS.

**Evidence for Prac 4:**

- Site loads at a **localhost** URL with WordPress theme and Vegely pages
- Local app shows site status **Running**
- Local → **Database** opens Adminer/phpMyAdmin with WordPress tables
- Editing a page in wp-admin updates the frontend without editing PHP/HTML files directly

### Screenshots submitted / demonstrated

1. Browser homepage at `http://vegely.local` with **URL bar visible**
2. (Optional) Menu or About page on localhost
3. (Optional) LocalWP app showing site **Running**
4. (Optional) Database admin showing `wp_posts` table

> **Note:** If `vegely.local` shows "connection refused", the LocalWP site is stopped — open the **Local** app and click **Start site**.

### Hosted vs local — comparison

| | Joomla (AwardSpace) | WordPress (InfinityFree) | WordPress (LocalWP) |
|--|---------------------|--------------------------|---------------------|
| Access | Public internet | Public internet | My machine only |
| Purpose | Week 2 assignment | Prac 3 submission | Prac 4 local demo |
| Database | Host MySQL | Host MySQL | Local MySQL |
| URL | vegely.atwebpages.com | vegely.site.je/wp/ | vegely.local |

### Deployment options (research)

I have not fully automated Local → production yet, but I researched these approaches:

1. **Manual:** Export MySQL dump + copy `wp-content` via FTP/File Manager to the host; run search-replace on URLs (`vegely.local` → live domain).
2. **Migration plugin:** **All-in-One WP Migration** or **Duplicator** — export local site as a file, import on InfinityFree (watch free tier size limits).
3. **Recreate on host:** Install WordPress on the host and re-import content (WXR export / setup script) — what I used for InfinityFree.

**Challenges to expect when deploying:**

- URL changes in database and content links
- PHP version differences between local and host
- File upload limits on free hosting
- WordPress installed in subfolder (`/wp/`) vs site root

### Challenges and how I solved them

| Problem | Solution |
|---------|----------|
| `vegely.local` — ERR_CONNECTION_REFUSED | Open LocalWP → select **vegely** site → **Start site** → wait for **Running** |
| Local site exists but public site is separate | Treated Local as dev sandbox; public site on InfinityFree for submission |
| AwardSpace database limit blocked second CMS | Used InfinityFree for public WordPress instead |
| Large zip failed to extract on InfinityFree | Uploaded images folder-by-folder via File Manager |

### Plugins (assignment progress)

| Plugin | Purpose | Status |
|--------|---------|--------|
| Contact Form 7 | Contact page form | To install on public site |
| Yoast SEO / Rank Math | SEO meta descriptions | Optional |
| WordPress Importer | Import WXR pages | Used during setup |

### What I learned

- **LocalWP** is faster than manually configuring XAMPP + WordPress zip for local WordPress development.
- Local and production are **separate environments** — changes on localhost do not appear online until deployed.
- Understanding the stack (**browser → web server → PHP → MySQL**) helps debug issues (connection refused = server not running; 404 = wrong path; blank DB = install not finished).
- Free hosting works for learning but has constraints — plan hosting choice around database limits and DNS delay.
- For this subject, I now have three Vegely deployments: static (Week 1), Joomla (Week 2), WordPress local + public (Week 3–4).

### Links

- **Local (Prac 4):** http://vegely.local
- **Public WordPress (Prac 3):** [https://vegely.site.je/wp/](https://vegely.site.je/wp/)
- **Joomla (Week 2):** http://vegely.atwebpages.com/
- **Static site (Week 1):** [vegelyweb.vercel.app](https://vegelyweb.vercel.app)
