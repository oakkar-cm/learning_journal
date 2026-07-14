## Learning journal entry — Week 5 (Prac 5)

**Title:** WordPress child themes — separating brand design from the parent theme

**Date:** July 2026  
**Subject:** CP3402 — Content Management Systems  
**Practical:** Prac 5 — WordPress Child Themes

---

### What I did this week

- Built a **WordPress child theme** for my **Vegely** startup site on **Twenty Twenty-Five**
- Created theme folder **`twentytwentyfive-vegely`** with the required files:
  - `style.css` — theme header including `Template: twentytwentyfive`
  - `functions.php` — enqueues parent stylesheet first, then child stylesheet
- Applied **seven visible CSS customisations** (sticky header, typography, navigation, buttons, links, hidden duplicate page title)
- Used the browser **Inspector** to find block-theme selectors (`.wp-block-navigation`, `.wp-block-button__link`, etc.) before writing CSS
- Zipped the theme as **`twentytwentyfive-vegely.zip`** for LearnJCU submission
- Drafted a **LinkedIn post** about one lesson from this subject (see below)

### Context — from Additional CSS to a child theme

Earlier in the subject I styled Vegely using **Appearance → Customize → Additional CSS** on the parent theme. That worked for Assignment 1, but every rule lived in the database, not in version-controlled theme files. Prac 5 pushed me to move the same brand ideas into a **child theme** so:

- Parent theme updates are less likely to wipe my work
- CSS lives in `style.css` where I can zip and submit it
- I follow the [WordPress child theme pattern](https://developer.wordpress.org/themes/advanced-topics/child-themes/) from class notes

### Child theme structure

```
wp-content/themes/twentytwentyfive-vegely/
├── style.css       — Theme Name, Template: twentytwentyfive, Vegely brand CSS
└── functions.php   — wp_enqueue_style() for parent + child
```

### style.css header (parent reference)

```css
/*
Theme Name: Vegely Child
Template: twentytwentyfive
Author: Oakkar Phyoe
Version: 1.0.0
*/
```

The **`Template:`** line must match the parent folder name exactly (`twentytwentyfive`). If it is misspelled, WordPress will not recognise the child theme.

### functions.php — enqueue pattern

```php
wp_enqueue_style(
    'twentytwentyfive-parent-style',
    get_template_directory_uri() . '/style.css',
    array(),
    $parent->get( 'Version' )
);

wp_enqueue_style(
    'twentytwentyfive-vegely-style',
    get_stylesheet_uri(),
    array( 'twentytwentyfive-parent-style' ),
    wp_get_theme()->get( 'Version' )
);
```

Child styles load **after** the parent so my rules can override Twenty Twenty-Five defaults.

### Seven visible customisations

| # | What changed | CSS target | Why it matters for Vegely |
|---|--------------|------------|---------------------------|
| 1 | Site-wide **Segoe UI** font and dark green body text | `body`, `.entry-content p` | Matches Joomla Cassiopeia look across both assignment sites |
| 2 | **Sticky frosted header** with light border | `header.wp-block-template-part` | Navigation stays visible while scrolling long Home page |
| 3 | **Bold site title** in brand ink colour | `.wp-block-site-title a` | “Vegely” reads as a product brand, not default theme text |
| 4 | **Green navigation hover** | `.wp-block-navigation-item__content:hover` | Clear affordance on menu items |
| 5 | **Pill-shaped green buttons** | `.wp-block-button__link` | “Build my plan” CTAs match startup marketing style |
| 6 | **Hidden duplicate page title** | `.entry-header`, `.wp-block-post-title` | Custom HTML heroes already include `<h1>` — avoids double headings |
| 7 | **Green content links** with hover state | `.entry-content a` | Readable links without breaking button styles |

### Workflow: Inspector → CSS file

1. Open https://vegely.site.je/wp/ in Chrome or Edge  
2. Right-click an element → **Inspect**  
3. Edit colours/fonts in the Styles panel until it looks right  
4. Copy the selector and property into `style.css`  
5. Refresh with child theme active to confirm

This was faster than guessing class names for the block editor theme.

### Challenges and how I solved them

| Problem | Solution |
|---------|----------|
| Block theme class names differ from classic themes | Inspected live Vegely pages; targeted `.wp-block-*` classes |
| Child theme not listed in Appearance → Themes | Checked folder is under `wp-content/themes/`; verified `Template: twentytwentyfive` spelling |
| Styles not overriding parent | Enqueued parent CSS first; child CSS second with dependency array |
| Already had hundreds of lines in Additional CSS | Moved **theme-level** rules (header, nav, buttons, typography) into child theme; left page-layout helpers in Customizer for now |
| Parent theme must stay installed | Kept Twenty Twenty-Five installed; only **activated** the child theme |

### LinkedIn reflection (for Prac 5)

**Profile:** [linkedin.com/in/oakkar-phyoe-206375324](https://www.linkedin.com/in/oakkar-phyoe-206375324/)

**Lesson:** Building the same startup in **WordPress and Joomla** taught me that a CMS is not just a template picker — it is a **stack of decisions** (content model, theme layer, plugins, hosting limits). Child themes are a small example of that: you customise **without breaking the upgrade path** of the parent. That mindset — separate what you own from what the platform owns — is what I want to carry into industry work.

**Copy this post** (LinkedIn → Start a post → paste → publish):

```
Week 5 in my CMS subject at JCU: I built a WordPress child theme for my Vegely startup site.

Biggest lesson so far: a real website is more than picking a theme. You need to know where your changes live — Customizer CSS vs theme files vs plugins — and what happens when the parent theme updates.

Child themes let me keep Twenty Twenty-Five updatable while my brand styling (colours, navigation, buttons, typography) stays in files I control. I built the same Vegely idea in Joomla and WordPress this semester, and that forced me to think about structure, not just pages.

Still learning — but this is the kind of workflow I want in industry.

#WordPress #WebDevelopment #JCU #LearningInPublic
```

**After publishing:** open the post → **⋯** → **Copy link to post** → paste below (LearnJCU wants the **post** URL, not just your profile).

**LinkedIn post URL:** _[paste link to the specific post after you publish]_

### What I learned

- A child theme for CSS-only work needs just **`style.css` + `functions.php`** — no PHP templates required unless you override template files later
- `Template:` in the child header must match the **parent folder name** on disk (`twentytwentyfive`, not “Twenty Twenty-Five”)
- Block themes (FSE) still use the same enqueue pattern as classic themes
- Inspector → CSS is a practical bridge between design tweaks and maintainable theme code
- Moving from Customizer CSS to a child theme clarified **what belongs in the theme layer** vs what belongs in page content
- Publishing a short LinkedIn reflection forces me to explain technical work in plain language — useful for teamwork and job applications

### Submission checklist (Prac 5)

- [x] Zip: `twentytwentyfive-vegely.zip`
- [ ] LinkedIn post published on [my profile](https://www.linkedin.com/in/oakkar-phyoe-206375324/) + **post URL** added above
- [x] Learning journal: this entry → https://github.com/oakkar-cm/learning_journal/blob/main/week5.md
- [ ] (Optional) Upload and activate child theme on https://vegely.site.je/wp/

### Links

- **WordPress site:** [https://vegely.site.je/wp/](https://vegely.site.je/wp/)
- **Joomla site (Assignment 1):** [http://vegely.atwebpages.com/](http://vegely.atwebpages.com/)
- **Child theme (local project):** `CMS-A1/prac5-submit/twentytwentyfive-vegely/`
- **WordPress child themes docs:** [developer.wordpress.org — Child Themes](https://developer.wordpress.org/themes/advanced-topics/child-themes/)
- **LinkedIn profile:** [linkedin.com/in/oakkar-phyoe-206375324](https://www.linkedin.com/in/oakkar-phyoe-206375324/)
- **Learning journal repo:** [github.com/oakkar-cm/learning_journal](https://github.com/oakkar-cm/learning_journal)
