# 🍛 Family Meal Planner Dashboard — Implementation Plan

## Problem
Build a single-file, no-server meal plan tracking dashboard for a family of 3 (Rahul, Nabanita, Vedanshi) — vegetarian, exploring diverse Indian **and international** cuisines.

## Requirements (confirmed)
| Requirement | Detail |
|---|---|
| Tech stack | Single HTML/CSS/JS file, no frameworks, no server |
| Family | Rahul, Nabanita, Vedanshi |
| Meal slots | Breakfast, Lunch, Snack, Dinner |
| Horizon | Weekly (7 days, Mon–Sun) |
| Persistence | JSON file export/import + localStorage fallback |
| Features | Recipe bank, random shuffle, grocery list, print view, dinner vote, roulette |
| Cuisines | Indian (7 regions) + Mexican, Thai, Italian, Chinese, Japanese, Korean, Middle Eastern, Mediterranean |

## Architecture
Single `index.html` file (hosted on GitHub Pages) containing:
- Embedded CSS (responsive, mobile-scrollable nav, print-friendly)
- Embedded JS (all logic, recipe data, persistence)
- No external dependencies
- **Live at:** https://nabanita-maj.github.io/meal-planner/
- **Repo:** https://github.com/nabanita-maj/meal-planner

## Tabs (in UI order)
🗳️ Vote → 🎰 Roulette → 📅 Planner → 📖 Recipes → 🛒 Grocery → 🧑‍🍳 Prep → 🏪 Pantry

## Todos (all completed ✅)

### 1. ✅ scaffold — Create project directory & HTML shell
### 2. ✅ recipe-bank — Build vegetarian recipe data
- **65 Indian** + **52 international** = **117 built-in recipes**
- Each recipe includes: `prep` (minutes), `cook` (minutes), `prepAhead` (list of weekend prep tasks)
- Indian regions: North Indian, South Indian, Bengali, Gujarati, Maharashtrian, Rajasthani, Pan-Indian
- International: Mexican (12), Thai (10), Italian (12), Chinese (6), Japanese (2), Korean (2), Middle Eastern (6), Mediterranean (2)
### 3. ✅ ui-nav — Sticky nav bar with horizontally-scrollable tab bar + scroll hint for mobile
### 4. ✅ weekly-planner — Week grid with prep time badges (⏱) on each cell
### 5. ✅ dish-picker — Modal showing prep+cook times per dish
### 6. ✅ auto-fill — One-click random week fill + clear week
### 7. ✅ recipe-browser — Filterable recipe cards with prep times, prep-ahead tips, and cuisine grouping
### 8. ✅ grocery-list — Auto-generated categorized grocery list from planned meals
### 9. ✅ persistence — localStorage auto-save + JSON file export/import (meals, pantry, votes, custom recipes)
### 10. ✅ print-view — Print-friendly CSS hiding non-essential UI
### 11. ✅ responsive — Mobile-friendly layout with scrollable nav, single-column grids
### 12. ✅ weekend-prep — Smart prep guide (Friday night → Saturday → Sunday → weekday tips)
### 13. ✅ pantry-tracker — Check off in-stock items, see what's missing for the week, add/remove custom ingredients
### 14. ✅ ingredient-lookup — Search any ingredient to see all dishes that use it
### 15. ✅ recipe-roulette — Animated spinning wheel weighted by pantry match %, filter by meal/cuisine
### 16. ✅ dinner-vote — Daily family poll (Rahul/Nabanita/Vedanshi), auto-populated from planned dinner + random suggestions, winner banner, vote history
### 17. ✅ recipe-crud — Add custom recipes via form modal, delete any recipe with ✕ button, custom recipes tagged with green badge
### 18. ✅ mobile-nav-fix — Tab bar scrolls horizontally on mobile with gradient scroll hint

## Notes
- All code lives in one file — CSS in `<style>`, JS in `<script>`
- Recipe data is a JS array of objects (no external fetch)
- Custom recipes and deleted built-ins persist in localStorage separately
- localStorage is the live store; JSON export is the "save to disk" mechanism
- Print uses `window.print()` with CSS hiding non-essential UI
- Region filter uses `<optgroup>` to separate Indian vs International cuisines
- Grocery categories cover both Indian and international ingredients
- Vote tab is the default landing page (most engaging for family use)
