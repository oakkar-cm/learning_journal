## Learning journal entry — Week 5 (Prac 5)

**Title:** WordPress child themes and professional reflection

### What I did this week

- Created a **WordPress child theme** for my Vegely site: `twentytwentyfive-child`
- Parent theme: **Twenty Twenty-Five** (`Template: twentytwentyfive` in `style.css`)
- Followed [WordPress child theme developer docs](https://developer.wordpress.org/themes/advanced-topics/child-themes/): theme folder inside `wp-content/themes/`, `style.css` with parent template comment, and `functions.php` to enqueue parent + child styles
- Applied **8 visible customisations** using CSS (brand colours, typography, navigation, buttons, footer, links, images)
- Used browser **Inspector** to preview selectors, then copied rules into `style.css`
- Packaged the theme as **`twentytwentyfive-child.zip`** for prac submission
- Wrote a **LinkedIn post** reflecting on one lesson from this subject (CMS + deployment)

### Child theme structure

```
wp-content/themes/twentytwentyfive-child/
├── style.css       — theme header + Vegely brand CSS
├── functions.php   — wp_enqueue_style for parent, child, Google Fonts
└── readme.txt
```

### style.css header (parent reference)

```css
/*
 Theme Name:   Vegely Child (Twenty Twenty-Five)
 Template:     twentytwentyfive
 ...
*/
```

### functions.php — enqueue pattern

```php
wp_enqueue_style( 'twentytwentyfive-parent', get_template_directory_uri() . '/style.css', ... );
wp_enqueue_style( 'twentytwentyfive-child', get_stylesheet_uri(), array( 'twentytwentyfive-parent' ), ... );
```

### Six+ visible customisations

| # | Customisation | CSS target |
|---|---------------|------------|
| 1 | Cream/green gradient **page background** | `body`, `.wp-site-blocks` |
| 2 | **Poppins** display headings | `h1–h6`, `.wp-block-site-title` |
| 3 | **Green site title** brand colour | `.wp-block-site-title a` |
| 4 | **Navigation** pill hover (green tint) | `.wp-block-navigation a` |
| 5 | **Buttons** — green gradient, rounded pill, glow shadow | `.wp-block-button__link` |
| 6 | **Footer** — dark green background, light text, top accent border | `footer`, `.site-footer` |
| 7 | **Content links** — green accent + underline offset | `.wp-block-post-content a` |
| 8 | **Images** — rounded corners + soft shadow | `.wp-block-image img` |

### Why use a child theme?

- **Safe updates:** Parent theme (Twenty Twenty-Five) can update without wiping my CSS
- **Organisation:** Brand styles live in one place (`style.css`) instead of the Customiser or Additional CSS box
- **Best practice:** Recommended by WordPress for any theme customisation beyond minor tweaks

### Challenges and how I solved them

| Problem | Solution |
|---------|----------|
| Block theme uses different class names than classic themes | Used browser Inspector on live Vegely pages to find `.wp-block-navigation`, `.wp-block-button__link`, etc. |
| Child styles not loading | Ensured `functions.php` enqueues **parent** style first, then child with dependency array |
| Theme not appearing in admin | Checked folder name matches slug; verified `Template: twentytwentyfive` spelling matches parent folder |
| Parent must stay installed | Kept Twenty Twenty-Five installed; only activated child theme |

### LinkedIn reflection

I published a post about learning that **building a real site means more than picking a template** — understanding CMS architecture (content, themes, plugins, hosting limits) makes you a stronger developer and teammate. See prac submission for post URL.

*(Add your LinkedIn post URL below after publishing.)*

**LinkedIn post:** _[paste URL here]_

### What I learned

- Child themes need only `style.css` + `functions.php` for CSS-only customisation; template overrides go in matching PHP files if needed later
- `Template:` in the child `style.css` header must exactly match the **parent theme folder name** (`twentytwentyfive`)
- Block themes (FSE) still load child `style.css` via `wp_enqueue_scripts` — same pattern as classic themes
- Inspector → CSS file is a fast workflow for visible tweaks before committing to the child theme
- Professional visibility (LinkedIn) helps frame technical work as communication, not just coding

### Submission checklist

- [x] Zip: `twentytwentyfive-child.zip`
- [ ] LinkedIn post link
- [x] Learning journal: this file
- [ ] Activate child theme on https://vegely.site.je/wp/ (upload zip to `wp-content/themes/`)

### Links

- **WordPress site:** [https://vegely.site.je/wp/](https://vegely.site.je/wp/)
- **Child theme (local):** `wp-content/themes/twentytwentyfive-child/`
- **WordPress child themes docs:** https://developer.wordpress.org/themes/advanced-topics/child-themes/
