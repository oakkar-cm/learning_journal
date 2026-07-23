## Learning journal entry — Week 7 (Prac 7)

**Title:** PHP skills demo + group sprint work  
**Date:** July 2026  
**Subject:** CP3402  
**Practical:** Prac 7 — PHP (+ group project)

---

### Learning activities — individual PHP site

I built an original mini-site called **Vegely Plan Preview** (not copied from a PHP tutorial). It has two pages that share a header and footer.

**Files submitted:** `index.php`, `about.php`, `includes/header.php`, `includes/footer.php`, `includes/functions.php`, `assets/style.css`

| Skill | How I demonstrated it |
|-------|------------------------|
| echo | Hero headings, HTML lists, skill checklist strings |
| if / elseif / else | Morning/afternoon/evening tip; plan label from meal count |
| for | Days 1–7 meal slots |
| while | Countdown tip list |
| foreach + array | Sample meals table; about-page reasons list |
| Functions with parameters | `vegely_greet($name)`, `vegely_format_sgd($amount)`, `vegely_plan_label($meals)` |
| include | Both pages include shared header and footer |

I tested locally with PHP’s built-in server (`php -S localhost:8000`) and checked Home + About both show the same nav/footer.


### What I learned

- `include` / `require` keep layout DRY across pages
- Mixing HTML and PHP is clearer when logic lives in small functions
- Individual prac work and group sprint work can run in the same week — journal both briefly
- Markers can see PHP skills on the pages themselves if the code is commented and structured

### Links

- Journal: https://github.com/oakkar-cm/learning_journal/blob/main/week7.md  
- Group Slack: https://app.slack.com/client/T0BF3Q2SXP1/C0BGDFQT3SL  
- Discord: https://discord.gg/cX5CHUjm  
- Group GitHub: https://github.com/Minthawphyo/cp3402-2026-teamCharlie  
- Trello: https://trello.com/b/5tKfE4KR/cms
