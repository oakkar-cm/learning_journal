## Learning journal entry — Week 2

**Title:**  Building the Vegely startup site with Joomla

### What I did this week

- Installed **Joomla 5** locally using **XAMPP** (Apache + MySQL) at `C:\xampp\htdocs\Vegety` for development and testing.
- Deployed the site to **AwardSpace** free hosting using the **Zacky Joomla installer**, with the live URL **http://vegely.atwebpages.com/** (subdomain provided by AwardSpace / atwebpages.com).
- Chose the **Cassiopeia** template and customised it so the site no longer looks like a default Joomla install.
- Built a startup concept: **Vegely** — premium healthy food delivery in Singapore.
- Created four main pages as Joomla articles: **Home**, **Menu**, **About**, and **Cart**.
- Set up the **Main Menu** with navigation linking to each page.
- Customised the template with:
  - Custom CSS (`user.css`) — green brand colours, glass-style cards, spacing, footer
  - Custom JavaScript (`user.js`) — scroll animations, cart, mobile nav, menu tabs
  - Custom header layout (`navbar-vegely.php`) — centred nav links, cart chip, contact button
  - Custom footer (`vegely-footer.php`) — newsletter, links, contact info
- Added **startup images** (hero photos, menu dishes, team portraits) under template media and `images/vegely/`.
- Configured template style in Joomla admin/DB: site title **Vegely**, alternative colour scheme, fluid layout, Google fonts (Inter + Poppins).
- Hid Joomla-default elements (breadcrumbs, article metadata) for a cleaner marketing-site look.
- **Published the site online:** exported the local database, uploaded custom template files via **FTP** to AwardSpace (`f32-preview.awardspace.net`), and fixed missing core files so the live site matches the local Vegely design.

### Challenges and how I solved them

| Problem | Solution |
|---------|----------|
| Live site showed default Joomla / blank page after AwardSpace install | Imported local database; uploaded custom template via FTP; restored missing root `index.php` |
| FTP login failed with wrong hostname | Used AwardSpace FTP details from control panel (`f32-preview.awardspace.net`, port 21) |
| AwardSpace default “Welcome” page instead of Joomla | Removed stray `index.html` and uploaded Joomla `index.php` to the site root |
| Article content invisible (fade-up CSS) | Added `user.js` to toggle `.is-visible` on scroll |
| Articles not showing in admin | Fixed Joomla 5 workflow associations in the database |
| Large gaps between nav and content | Reduced padding in CSS; synced template + media CSS files |
| Missing footer | Added `vegely-footer.php` include in `index.php` |
| Broken / missing images | Downloaded food and team photos into `media/templates/site/cassiopeia/images/` |

### What I learned

- How Joomla separates **content** (articles), **structure** (menus), **presentation** (templates), and **modules** (reusable blocks).
- Template overrides live in `templates/cassiopeia/html/` and load instead of core layouts.
- User assets (`user.css`, `user.js`) extend Cassiopeia without editing core files.
- Joomla 5 requires workflow associations for articles to appear correctly in the admin UI.
- Cache must be cleared after template/CSS changes (`System → Clear Cache` or CLI).
- How to use **AwardSpace** for free Joomla hosting: install via Zacky installer, manage files through **FTP Manager** or File Manager, and deploy a local site by importing a database and uploading template overrides.
- A local XAMPP site and a live AwardSpace site are separate — custom files and `index.php` must be uploaded to the hosting account; the database alone is not enough.
