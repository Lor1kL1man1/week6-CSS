# Exercise 5 — Responsive Design & Media Queries
**⏱ Estimated time: 15 minutes**

---

## Why Responsive Design Matters

More than **60% of web traffic** comes from mobile devices. A website that only looks good on desktop is an incomplete website.

The **mobile-first** approach means:
1. Write your base CSS for the **smallest screen** (mobile)
2. Add `@media` queries to adjust the layout for **larger screens**

This is easier than it sounds — most of your styles already work fine on mobile. You just need to unlock the multi-column layouts for bigger screens.

---

## The Viewport Meta Tag

Make sure this is in your `<head>` (it's already in the starter HTML):

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Without this, mobile browsers zoom out and show a tiny desktop version.

---

## Tasks

### 1. Make Images Responsive (1 min)

Add this globally so images never break out of their container:

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

### 2. Mobile Base Styles (4 min)

Review your existing CSS and make sure these are set (no media query needed — these are the defaults):

```css
/* Single-column project grid on mobile */
.projects-grid {
  grid-template-columns: 1fr;
}

/* Stacked about section on mobile */
.about-content {
  flex-direction: column;
}

/* Smaller headings on mobile */
h1 { font-size: 2rem; }
h2 { font-size: 1.5rem; }
```

---

### 3. Tablet Breakpoint — 768px (5 min)

Add this media query block at the bottom of your CSS:

```css
@media (min-width: 768px) {
  h1 { font-size: 3rem; }
  h2 { font-size: 2rem; }

  .about-content {
    flex-direction: row;    /* Side by side */
    align-items: flex-start;
  }

  .projects-grid {
    grid-template-columns: repeat(2, 1fr);  /* 2 columns */
  }

  .nav-links {
    display: flex;          /* Show nav links (hidden on mobile) */
  }
}
```

---

### 4. Desktop Breakpoint — 1024px (5 min)

```css
@media (min-width: 1024px) {
  h1 { font-size: 4rem; }

  .container {
    max-width: 1100px;
    margin: 0 auto;
  }

  .projects-grid {
    grid-template-columns: repeat(3, 1fr);  /* 3 columns */
  }
}
```

---

## Testing Responsiveness

1. Open your page in Chrome or Firefox
2. Press **F12** to open DevTools
3. Click the **phone/tablet icon** (or press **Ctrl+Shift+M**)
4. Test at these sizes:
   - **iPhone SE** → 375px
   - **iPad** → 768px
   - **Desktop** → 1280px

✅ **Check each size and fix anything that looks broken.**

---

## Common Breakpoints

| Name | Width | What changes |
|------|-------|-------------|
| Mobile | default (< 481px) | Single column, stacked layout |
| Small tablet | 481px | 2-column grid |
| Tablet | 768px | Horizontal nav, side-by-side about, 2-col grid |
| Desktop | 1024px | 3-col grid, max-width container |
| Wide | 1440px | Slightly larger base font size |

---

## 🌟 Bonus — Responsive Font Sizes with `clamp()`

`clamp(min, preferred, max)` lets font sizes scale smoothly with the viewport:

```css
h1 {
  font-size: clamp(2rem, 5vw, 4rem);
  /* Min: 2rem | Preferred: 5% of viewport width | Max: 4rem */
}
```

This eliminates the need for separate media queries just for font sizes!
