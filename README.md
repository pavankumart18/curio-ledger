# Curio Ledger

Curio Ledger is a static, card-based archive of daily research stories.
Each topic lives in its own folder under `topics/` and is linked from the main dashboard at `index.html`.

## Current Snapshot

- **Main dashboard:** `index.html`
- **Latest entry:** `topics/april_26_2026/index.html`
- **Total topic pages:** 14
- **Tech stack:** Plain HTML/CSS/JS (some topic pages also use CDN libraries such as Tailwind and Chart.js)

## Project Structure

```text
Daily topic/
├── index.html                  # Main dashboard (all cards listed here)
└── topics/
    ├── april_26_2026/
    │   └── index.html          # One daily story page
    ├── april_2_2026/
    │   └── index.html
    └── ...                     # More date/topic folders
```

## How to Add a New Daily Story

1. Create a new folder inside `topics/`:
   - Example: `topics/april_27_2026/`
2. Add your story page:
   - `topics/april_27_2026/index.html`
3. Open root `index.html` and add a new card inside the `.grid` section.
4. Place the new card near the top if it is the latest date.
5. Update card details:
   - `href` to your new topic path
   - Card image (`src`, optional `srcset`)
   - `alt` text
   - Meta line (date + category)
   - Title and short lede text
6. (Optional) Add a new dot theme class if you want custom card accent dots:
   - Example: `.card-dots--newtopic i:nth-child(...) { ... }`
7. Save and open `index.html` in a browser to verify:
   - New card appears
   - Link opens the new topic page
   - Search can find the new card text

## Dashboard Update Checklist (Use Every Time)

- New topic folder exists in `topics/`
- New topic has `index.html`
- Card added to root `index.html`
- Card `href` path is correct
- Card text (date/title/category) is correct
- Image loads and has meaningful `alt` text
- No broken layout in desktop/mobile
- Search still works with new card

## Naming Convention

Use lowercase snake-style folder names by date:

- `march_24_2026`
- `april_1_2026`
- `april_26_2026`

If multiple stories are created on the same date, use a suffix:

- `march_29_2026_1`
- `march_29_2026_2`

## Maintenance Notes

- Keep cards ordered by recency for easy browsing.
- Keep ledes short so card heights remain visually balanced.
- Prefer compressed images for faster loading.
- Avoid committing OS metadata files like `.DS_Store`.

## Optional Git Hygiene

If you want to stop tracking `.DS_Store` files in this repo:

1. Add this line to `.gitignore`:

   ```gitignore
   .DS_Store
   ```

2. Remove already tracked `.DS_Store` files from Git index:

   ```bash
   git rm --cached .DS_Store topics/.DS_Store
   ```

3. Commit the cleanup.

---

If you want, I can also add a small reusable **card template snippet** to this README so you can paste a new dashboard card in seconds.
