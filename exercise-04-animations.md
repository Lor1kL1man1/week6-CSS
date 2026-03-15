# Exercise 4 — CSS Transitions & Animations
**⏱ Estimated time: 15 minutes**

---

## Two Ways to Animate in CSS

| Technique | When to use |
|-----------|-------------|
| **Transitions** | Animate a change triggered by user interaction (hover, focus, click) |
| **Keyframe animations** | Animate automatically on load, or loop indefinitely |

> ⚡ **Performance rule:** For silky-smooth animations, only animate `opacity` and `transform`. These are GPU-accelerated. Avoid animating `width`, `height`, `margin`, or `padding` — they cause layout recalculations and stuttering.

---

## Tasks

### 1. Define the `fadeIn` Animation (3 min)

Add this `@keyframes` block near the top of the animations section in `style.css`:

```css
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

Now apply it to the hero elements with staggered delays:

```css
.hero h1 {
  animation: fadeIn 0.8s ease-out both;
}

.tagline {
  animation: fadeIn 0.8s ease-out 0.3s both; /* 0.3s delay */
}

.btn-primary {
  animation: fadeIn 0.8s ease-out 0.6s both; /* 0.6s delay */
}
```

✅ **Check:** Refresh the page — the hero text should fade in one element at a time.

---

### 2. Project Card Hover (4 min)

Add a transition and hover state to `.project-card`:

```css
.project-card {
  /* Add to existing styles: */
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.15);
}

.project-card a {
  /* Add to existing styles: */
  transition: background-color 0.2s ease;
}

.project-card a:hover {
  background: var(--color-primary);
}
```

✅ **Check:** Hover over a project card — it should lift up smoothly.

---

### 3. Nav Links Hover (3 min)

```css
.nav-links a {
  /* Add to existing styles: */
  transition: background-color 0.2s ease, color 0.2s ease;
}

.nav-links a:hover {
  background-color: var(--color-bg);
  color: var(--color-primary);
}
```

---

### 4. Skill Tags Hover (2 min)

```css
.skills-flex li {
  /* Add to existing styles: */
  transition: transform 0.2s ease, background-color 0.2s ease;
  cursor: default;
}

.skills-flex li:hover {
  transform: scale(1.05);
  background-color: var(--color-secondary);
  color: white;
}
```

---

### 5. Submit Button Press Effect (3 min)

```css
.btn-submit:hover {
  transform: translateY(-2px);
}

.btn-submit:active {
  transform: translateY(0); /* Press down on click */
}
```

✅ **Check:** Click the button — it should feel like a real physical button press.

---

## `transform` Quick Reference

```css
transform: translateX(20px);          /* Move right */
transform: translateY(-10px);         /* Move up */
transform: translate(20px, -10px);    /* Move right and up */
transform: scale(1.1);                /* 10% bigger */
transform: rotate(45deg);             /* Rotate */
transform: translateY(-8px) scale(1.02); /* Multiple at once */
```

---

## 🌟 Bonus — Pulse Animation

Add a looping pulse to your "Hire Me" button or contact link to draw attention to it:

```css
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50%       { transform: scale(1.05); }
}

.btn-primary {
  /* Add to existing styles: */
  animation: fadeIn 0.8s ease-out 0.6s both, pulse 2s ease-in-out 1.5s infinite;
}
```
