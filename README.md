# First Year Seminar: Course Guide Site

A static website that gives colleagues an overview of **First Year Seminar** (FYS), the Grade 9 health and technology course at The International School Nido de Aguilas. It covers the course goals, the four units, the proficiency scales, and links to teaching resources.

The site is plain HTML and CSS. It has no build step, no JavaScript framework and no dependencies beyond Google Fonts.

## Viewing the site

- **Locally:** open `index.html` in a browser.
- **With a local server:** from the `FYS_2026` folder, run:

  ```bash
  python3 -m http.server 8765 --directory site
  ```

  Then visit <http://localhost:8765>.
- **Hosting:** upload the whole `site/` folder to any static host, such as Google Sites (embed), GitHub Pages, Netlify or a school web server. All links between pages are relative.

## Structure

```
site/
├── index.html        Course overview: purpose, pillars, progression, unit cards, standards, resources
├── unit-1.html       Unit 1 · Habits of Action (AI Tools Expo)
├── unit-2.html       Unit 2 · Mental Health & the Teen Brain (Wellness Space Design Challenge)
├── unit-3.html       Unit 3 · Harm Reduction & Substances (PSA campaign)
├── unit-4.html       Unit 4 · Who Am I? Comprehensive Sexuality Education (Who Am I video, PSA)
├── standards.html    All nine proficiency scales (2.0 / 3.0 / 4.0) and a unit-by-standard grid
├── README.md
└── assets/
    ├── brand.css     Nido brand tokens and utilities (unchanged copy of ../style.css)
    ├── site.css      Layout and components for this site
    └── nido.jpg      School logo
```

Each unit page has the same sections:
1. Driving questions
2. Learning goals
3. Approach and norms
4. Lesson sequence
5. Assessments (with L-levels and standards, as labelled in Schoology)
6. Content topics (Units 3 and 4)
7. Resources

A sidebar summarizes the standards, key product and tools.

## Editing

- **Content:** edit the HTML for that page directly. Pages share the same header, nav and footer markup. If you add or rename a page, update the `<nav class="site-nav">` block on **every** page.
- **Branding:** colors and fonts come from `assets/brand.css`, which is a copy of the school style guide's `style.css`. If the style guide changes, replace this file. `site.css` builds on its variables (`--nido-blue`, `--nido-red`, `--nido-dark-gray`, `--font-gotham`).
- **Reusable components** in `site.css`:

  | Class | Use |
  |---|---|
  | `.unit-card` | Unit cards on the overview page |
  | `.sequence` + `.phase` | Numbered lesson list with phase headings. Continue numbering across lists with `style="counter-reset: seq N"` |
  | `.levels` | Proficiency-scale level table on the standards page |
  | `.lvl` (`.l3`, `.l2`, `.l1`) | L4 / L3 / L2 / L1.5 assessment badges |
  | `.tag` (`.health`, `.plain`) | Standard tags: red for health, blue for technology, gray for skills and dispositions |
  | `.callout`, `.topic`, `.resources`, `.checks`, `.dq-list` | Callout boxes, topic cards, resource link lists, goal checklists, question lists |

- **Adding a proficiency scale:** add an `<article class="scale" id="...">` to `standards.html`, add a row to the matrix table, and link the tag from the relevant unit pages and `index.html`.

## Sources

The content was compiled in October 2026 from these sources:

| Source | Used for |
|---|---|
| Schoology course export (`../Home-First-Year-Seminar-….imscc`) | Unit folders, graded tasks and their L-levels, resource links |
| `../units 1 and 2/` knowledge base | Units 1 and 2: lessons, routines, assessments |
| `../fys-unit-3/wiki`, `../fys-unit-4/wiki` | Units 3 and 4: scope and sequence, topic pages |
| `../proficiency scales/` | Scale descriptors |
| Health Communication scale (Google Doc) | Scale descriptors |
| Nido Skills & Dispositions deck | Skills and dispositions vocabulary |

Google Docs, Slides and Forms links point to the school's Drive. Viewers need a Nido account with access to open them.

## Related

- **Curriculum map (draft):** [FYS Curriculum Map 2026-2027](https://docs.google.com/spreadsheets/d/1qvY8lFnSuvk4BGI4oJbG-w3G-BzKZSd1u8Nhsi9Q8ko/edit), a Google Sheet with one column per unit. Its "To confirm" tab lists the open questions.

## Known gaps

- **Unit dates:** Units 1 and 2 give class-day numbers but no calendar dates. Unit 4's source material mixes 2025 and 2026 dates, so only day and month are shown.
- **Unfiled task:** "L4 – Innovative Designer – Final Design Packet and Work" sits at course level in Schoology and isn't shown on any unit page.
- **Personal values timed write:** Unit 4 lists it at L4, as in Schoology. The unit wiki describes an L3 timed writing instead.
