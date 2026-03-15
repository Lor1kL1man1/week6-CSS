# Exercise 6 — Polish: Shadows, Filters & CSS Variables
**⏱ Estimated time: 10 minutes**

---

## The Details That Make the Difference

These finishing touches elevate a *good-looking* page into a *great-looking* one. They are the details that make professional designs stand out.

---

## Tasks

### 1. Build Your Shadow System (3 min)

Add shadow variables to your `:root` block:

```css
:root {
  /* Add these alongside your existing variables */
  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.12);
  --shadow-lg: 0 16px 48px rgba(0, 0, 0, 0.18);
}
```

Now replace all hard-coded `box-shadow` values in your CSS with these variables:

```css
.project-card {
  box-shadow: var(--shadow-sm);
}

.project-card:hover {
  box-shadow: var(--shadow-lg);
}

.skills-flex li {
  box-shadow: var(--shadow-sm);
}
```

✅ **Check:** Hovering a card should show a stronger shadow.

---

### 2. Add a Spacing Scale (2 min)

```css
:root {
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 32px;
  --space-xl: 64px;
}
```

Optionally, update some of your `padding` and `margin` values to use these (e.g., `padding: var(--space-lg)`). This makes future redesigns much easier — change one variable and everything updates.

---

### 3. Profile Photo Grayscale Filter (2 min)

Find `.profile-photo` and add a filter that removes on hover:

```css
.profile-photo {
  filter: grayscale(80%);
  transition: filter 0.4s ease;
}

.profile-photo:hover {
  filter: grayscale(0%);
}
```

✅ **Check:** Hover over the profile photo — it should go from faded to full color.

---

### 4. Hero Dark Overlay with `::before` (3 min)

Add a semi-transparent dark layer over the hero gradient using a pseudo-element:

```css
.hero::before {
  content: '';
  position: absolute;
  inset: 0; /* shorthand for top:0; right:0; bottom:0; left:0 */
  background: rgba(0, 0, 0, 0.35);
}
```

Make sure the hero content appears **above** the overlay:

```css
.hero h1,
.hero .tagline,
.hero .btn-primary {
  position: relative; /* Puts content above the ::before overlay */
  z-index: 1;
}
```

> 🔑 This only works because `.hero` already has `position: relative` (set in Exercise 3).

✅ **Check:** The hero text should be slightly easier to read against a darkened gradient.

---

## CSS Filters Reference

```css
filter: grayscale(80%);               /* Desaturate */
filter: grayscale(0%);                /* Full color */
filter: brightness(0.7);              /* Darken */
filter: blur(4px);                    /* Blur */
filter: drop-shadow(2px 4px 8px rgba(0,0,0,0.3)); /* Shadow on PNG (respects transparency!) */
```

> 💡 `drop-shadow()` in `filter` is different from `box-shadow`. It follows the actual shape of a PNG image, including transparent areas. Perfect for logos and icons!

---

## 🌟 Bonus — Dark Mode

CSS variables make implementing a dark mode incredibly easy:

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-bg:   #0f172a;
    --color-text: #e2e8f0;
    --color-white: #1e293b;
  }
}
```

Try enabling dark mode on your operating system and see if your page automatically adapts!

---

## ✅ Final Checklist

You've completed all 6 exercises! Before submitting, check that your portfolio has:

- [ ] Flexbox on About section (image + text side by side)
- [ ] Flexbox on Skills section (wrapping tags)
- [ ] CSS Grid on Projects section (auto-filling cards)
- [ ] Sticky header with `z-index`
- [ ] Fixed back-to-top button
- [ ] Hero entrance animation (`@keyframes fadeIn`)
- [ ] Hover effects on cards, buttons, and nav links (with `transition`)
- [ ] Mobile-first layout with media queries at 768px and 1024px
- [ ] All images with `max-width: 100%`
- [ ] Shadow, spacing, and color CSS variables in `:root`
- [ ] Profile photo grayscale filter that colorizes on hover
- [ ] Hero dark overlay using `::before`

🎓 **Congratulations — you've completed the full HTML + CSS module!**
