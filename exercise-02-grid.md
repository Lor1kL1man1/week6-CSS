# Exercise 2 — CSS Grid
**⏱ Estimated time: 15 minutes**

---

## What is CSS Grid?

While Flexbox is one-dimensional (row **or** column), CSS Grid is **two-dimensional** — it controls **both rows and columns** at the same time. Grid is perfect for page-level layouts, card grids, and photo galleries.

> ⭐ **Rule of thumb:** Use Flexbox for a single row or column of items. Use Grid when you need items to align both horizontally AND vertically.

---

## Tasks

### 1. Build the Projects Grid (10 min)

Open `style.css` and find `.projects-grid`. Apply a responsive CSS Grid:

```css
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 24px;
  margin-top: 40px;
}
```

The magic here is `repeat(auto-fill, minmax(280px, 1fr))`:
- Each card is **at least 280px** wide
- Cards grow to fill available space (`1fr`)
- The browser automatically fits as many columns as possible

✅ **Check:** With a wide browser you should see 3 cards in a row. Shrink it and they should drop to 2, then 1.

---

### 2. Style the Project Cards (5 min)

Find `.project-card` and give it a polished look:

```css
.project-card {
  background: white;
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
  border-top: 4px solid var(--color-secondary);
}
```

Style the "View Project" link inside each card:

```css
.project-card a {
  display: inline-block;
  padding: 8px 20px;
  background: var(--color-secondary);
  color: white;
  border-radius: 4px;
  font-size: 0.9rem;
}
```

✅ **Check:** Each card should have a colored top border, white background, and a styled link at the bottom.

---

## Key Properties Reference

| Property | Example | What it does |
|----------|---------|--------------|
| `display: grid` | | Activates Grid on the parent |
| `grid-template-columns` | `repeat(3, 1fr)` | 3 equal columns |
| `grid-template-columns` | `repeat(auto-fill, minmax(250px, 1fr))` | Responsive columns |
| `gap` | `24px` | Space between rows and columns |
| `grid-column: span 2` | | Item spans 2 columns |
| `grid-column: 1 / -1` | | Item spans full width |

---

## 🌟 Bonus — Named Grid Areas

Try creating a full page layout with named areas. Add this to a new `.page-layout` container:

```css
.page-layout {
  display: grid;
  grid-template-areas:
    'header header header'
    'sidebar main   main  '
    'footer footer footer';
  grid-template-columns: 250px 1fr 1fr;
  grid-template-rows: auto 1fr auto;
}

/* Then assign each child to an area */
header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
main    { grid-area: main; }
footer  { grid-area: footer; }
```

This makes layouts extremely readable — the ASCII art in `grid-template-areas` shows exactly how the page is structured!
