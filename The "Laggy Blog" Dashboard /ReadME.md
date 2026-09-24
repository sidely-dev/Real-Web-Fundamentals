
---

### Project 3: Laggy Blog Dashboard

```markdown
# 🐢 Laggy Blog Dashboard
### Understanding Web Vitals by Breaking Them

> Intentionally build a slow, janky page — measure the damage with Chrome DevTools — then fix it.  
> The fastest way to truly understand Core Web Vitals.

![Status](https://img.shields.io/badge/Status-Educational%20Project-blue?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Web%20Vitals%20%7C%20Performance-orange?style=for-the-badge)
![Stack](https://img.shields.io/badge/Stack-Node.js%20%7C%20Express%20%7C%20Vanilla%20JS-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📌 About The Project

This project deliberately creates a poorly performing blog page so you can:

1. Measure real performance problems
2. Understand what each Web Vital actually means
3. Apply the correct fix and watch the metrics improve

You will intentionally break **CLS**, **TTFB/LCP**, and **FID**, then repair them one by one.

---

## 🎯 Learning Goals

- Understand Cumulative Layout Shift (CLS)
- Understand Time to First Byte (TTFB) and Largest Contentful Paint (LCP)
- Understand First Input Delay (FID) / Interaction to Next Paint
- Learn how to measure performance with Chrome DevTools (Lighthouse + Performance tab)
- Practice async data loading patterns that improve perceived performance

---

## 🧪 Experiments

### 1. Break CLS (Layout Shift)
- Place text above a large image
- Do **not** give the image width and height
- When the image finally loads, it pushes the text down violently
- Measure the high CLS score in Lighthouse
- **Fix**: Reserve space for the image (`width` + `height` or aspect-ratio)

### 2. Break TTFB & LCP
- Add a 3-second delay on the server before sending the HTML
- Measure the terrible TTFB
- **Fix**: Send the HTML shell immediately, then load the blog content asynchronously with `fetch()` + `async/await`
- Watch TTFB drop dramatically

### 3. Break FID (First Input Delay)
- On page load, run a heavy JavaScript loop (e.g. counting to 1 billion)
- Try clicking a button while the loop is running
- The button will feel frozen — that delay is FID
- **Fix**: Move heavy work off the main thread or defer it

---

## 🛠️ Tech Stack

| Part       | Technology              |
|------------|-------------------------|
| Backend    | Node.js + Express       |
| Frontend   | HTML + CSS + Vanilla JS |
| Measurement| Chrome DevTools (Lighthouse & Performance) |

---

## 📂 Project Structure

```text
laggy-blog/
│
├── backend/
│   ├── server.js             # Intentionally slow responses
│   └── package.json
│
├── frontend/
│   ├── index.html            # The laggy page
│   ├── styles.css
│   └── script.js             # Async loading + heavy loop
│
└── README.md
