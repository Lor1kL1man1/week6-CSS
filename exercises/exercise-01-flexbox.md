# Exercise 1 — CSS Flexbox
**⏱ Estimated time: 15 minutes**

---

## What is Flexbox?

Flexbox (Flexible Box Layout) is a **one-dimensional** layout system. It controls how items are arranged in a **row OR a column**. You activate it by adding `display: flex` to a **parent** element — that makes it a **flex container**, and all direct children become **flex items**.

---

## Tasks

### 1. Header Navigation (5 min)

Open `style.css` and find the `.header-inner` rule. Apply Flexbox so the logo sits on the left and the nav links sit on the right:

```css
.header-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 0;
}
```

Then make the nav links sit in a row with spacing:

```css
.nav-links {
  display: flex;
  gap: 24px;
}
```

✅ **Check:** Your logo should be on the left and nav links on the right.

---

### 2. About Section (5 min)

Find `.about-content` and apply Flexbox so the profile photo is on the left and the text is on the right:

```css
.about-content {
  display: flex;
  gap: 40px;
  align-items: flex-start;
}
```

Fix the image so it doesn't grow or shrink, and give the text all remaining space:

```css
.profile-photo {
  flex: 0 0 200px;
}

.about-text {
  flex: 1;
}
```

✅ **Check:** Shrink your browser window — the image and text should stay side by side until they don't fit.

---

### 3. Skills Section (5 min)

Find `.skills-flex` and make the skill tags wrap into rows:

```css
.skills-flex {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}
```

Style each skill tag so they look like chips:

```css
.skills-flex li {
  flex: 1 1 150px;
  padding: 12px 16px;
  border-radius: 6px;
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  text-align: center;
  font-weight: 600;
}
```

✅ **Check:** Resize the browser — skill tags should wrap to a new row when there's no more space.

---

## Key Properties Reference

| Container property | What it does |
|--------------------|--------------|
| `display: flex` | Activates Flexbox on the parent |
| `flex-direction: row` | Items go left → right (default) |
| `flex-direction: column` | Items go top → bottom |
| `justify-content: space-between` | Space between items on the main axis |
| `align-items: center` | Center items on the cross axis |
| `flex-wrap: wrap` | Allow items to wrap to the next line |
| `gap: 20px` | Space between items |

| Item property | What it does |
|---------------|--------------|
| `flex: 1` | Item grows to fill available space |
| `flex: 0 0 200px` | Fixed 200px, never grows or shrinks |
| `align-self: flex-end` | Override alignment for this item only |

---

## 🌟 Bonus

Try adding `justify-content: center` and `align-items: center` to `.hero` — it should perfectly center the hero text both horizontally and vertically! *(You'll do this properly in Exercise 3.)*
