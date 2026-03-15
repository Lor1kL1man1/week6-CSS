# Exercise 3 — CSS Positioning
**⏱ Estimated time: 10 minutes**

---

## The Five `position` Values

| Value | Behavior |
|-------|----------|
| `static` | Default. In the normal document flow. `top`/`left` have no effect. |
| `relative` | In the flow, but can be nudged with `top`/`right`/`bottom`/`left`. |
| `absolute` | Removed from flow. Positioned relative to the nearest **positioned** ancestor. |
| `fixed` | Always relative to the **browser window**. Stays on screen when scrolling. |
| `sticky` | Acts like `relative` until a scroll threshold, then acts like `fixed`. |

---

## Tasks

### 1. Sticky Header (3 min)

Find `.site-header` in `style.css` and make it stick to the top:

```css
.site-header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--color-white);
  border-bottom: 1px solid #e5e7eb;
}
```

✅ **Check:** Scroll down the page — the header should follow you and stay at the top.

---

### 2. Hero Section (4 min)

Find `.hero` and make it a full-viewport centered section:

```css
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  position: relative; /* needed for the ::before overlay in Exercise 6 */
  background: linear-gradient(135deg, var(--color-primary), var(--color-secondary));
  color: white;
}
```

✅ **Check:** The hero should fill the entire viewport height, with text centered in the middle.

---

### 3. Fixed Back-to-Top Button (3 min)

Find `.back-to-top` and pin it to the bottom-right corner of the screen:

```css
.back-to-top {
  position: fixed;
  bottom: 30px;
  right: 30px;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--color-accent);
  color: white;
  font-size: 1.2rem;
  font-weight: bold;
}
```

✅ **Check:** The button should always be visible in the bottom-right corner, even when you scroll.

---

## 🌟 Bonus — "NEW" Badge on a Card

Add a badge to one of your project cards. In `index.html`, add a `<span>` inside one `.project-card`:

```html
<div class="project-card">
  <span class="badge">NEW</span>
  <h3>Weather Dashboard</h3>
  ...
</div>
```

Then in `style.css`, make the card a positioned context and place the badge in the corner:

```css
.project-card {
  position: relative; /* Add this — makes .badge relative to the card */
}

.badge {
  position: absolute;
  top: -10px;
  right: -10px;
  background: var(--color-accent);
  color: white;
  font-size: 0.7rem;
  font-weight: 700;
  padding: 4px 10px;
  border-radius: var(--radius-full);
}
```

> 🔑 **Key rule:** For `position: absolute` to work relative to a specific parent, that parent must have `position: relative` (or any non-static value). Without this, the badge would position itself relative to the entire page!
