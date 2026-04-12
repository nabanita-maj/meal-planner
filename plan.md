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
| Features | Recipe bank, random shuffle, grocery list, print view |
| Cuisines | Indian (7 regions) + Mexican, Thai, Italian, Chinese, Japanese, Korean, Middle Eastern, Mediterranean |

## Architecture
Single `meal-planner.html` file containing:
- Embedded CSS (responsive, print-friendly)
- Embedded JS (all logic, recipe data, persistence)
- No external dependencies

## Todos (all completed ✅)

### 1. ✅ scaffold — Create project directory & HTML shell
### 2. ✅ recipe-bank — Build vegetarian recipe data
- **65 Indian** + **52 international** = **117 total recipes**
- Each recipe now includes: `prep` (minutes), `cook` (minutes), `prepAhead` (list of tasks)
- Indian regions: North Indian, South Indian, Bengali, Gujarati, Maharashtrian, Rajasthani, Pan-Indian
- International: Mexican (12), Thai (10), Italian (12), Chinese (6), Japanese (2), Korean (2), Middle Eastern (6), Mediterranean (2)
### 3. ✅ ui-nav — Navigation bar & tab system (5 tabs)
### 4. ✅ weekly-planner — Week grid with prep time badges (⏱) on each cell
### 5. ✅ dish-picker — Modal showing prep+cook times
### 6. ✅ auto-fill — One-click random week fill
### 7. ✅ recipe-browser — Recipe cards with prep times & prep-ahead tips
### 8. ✅ grocery-list — Auto-generated categorized grocery list
### 9. ✅ persistence — Save/Load JSON + localStorage (incl. pantry)
### 10. ✅ print-view — Print-friendly CSS
### 11. ✅ responsive — Mobile-friendly layout
### 12. ✅ weekend-prep — Smart prep guide (Friday night → Saturday → Sunday → weekday tips)
### 13. ✅ pantry-tracker — Check off in-stock items, see what's missing for the week
### 14. ✅ ingredient-lookup — Search any ingredient, see all dishes that use it
### 15. ✅ recipe-roulette — Spinning wheel weighted by pantry match, filter by meal/cuisine

## Notes
- All code lives in one file — CSS in `<style>`, JS in `<script>`
- Recipe data is a JS array of objects (no external fetch)
- localStorage is the live store; JSON export is the "save to disk" mechanism
- Print uses `window.print()` with CSS hiding non-essential UI
- Region filter uses `<optgroup>` to separate Indian vs International cuisines
- Grocery categories expanded with "Dairy & Cheese", "International Staples", and broader condiment/herb coverage
