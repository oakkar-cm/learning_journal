# Week 2

## Learning journal entry — Week 2

**Title:**  Building the Vegely startup site with Joomla

### What I did this week

- Installed **Joomla 5** locally using **XAMPP** (Apache + MySQL) at `C:\xampp\htdocs\Vegety`.
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

### Challenges and how I solved them

| Problem | Solution |
|---------|----------|
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
