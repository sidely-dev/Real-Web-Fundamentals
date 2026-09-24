# 🔀 Split-Personality Web App
### Understanding CORS & HttpOnly Cookies

> Two tiny servers on different origins that talk to each other — the best hands-on way to truly understand CORS and why HttpOnly cookies matter.

![Status](https://img.shields.io/badge/Status-Educational%20Project-blue?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-CORS%20%7C%20HttpOnly%20Cookies-orange?style=for-the-badge)
![Stack](https://img.shields.io/badge/Stack-Node.js%20%7C%20Express%20%7C%20Vanilla%20JS-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📌 About The Project

Instead of building one big application, this project runs **two separate servers** on your local machine:

- **Frontend Server (Origin A)** → `http://localhost:3000`
- **Backend Server (Origin B)** → `http://localhost:5000`

By forcing the browser to make cross-origin requests, you can clearly see how CORS works and why `HttpOnly` cookies are critical for security.

This is one of the most effective ways to learn these concepts because you can **see the browser block requests** and **watch cookies become invisible to JavaScript**.

---

## 🎯 Learning Goals

- Understand why browsers block cross-origin requests by default
- Learn how to properly configure CORS headers
- Observe the automatic **OPTIONS preflight** request
- See the difference between normal cookies and `HttpOnly` cookies
- Understand why JavaScript cannot read `HttpOnly` cookies (XSS protection)

---

## 🧪 Experiments

### 1. Trigger CORS (Watch it fail)
From the frontend (`localhost:3000`), try to `fetch()` data from the backend (`localhost:5000`).  
→ The browser will block the request and show a CORS error in the console.

### 2. Fix CORS
Add the correct `Access-Control-Allow-Origin` header on the backend.  
→ Watch the Network tab for the automatic **OPTIONS preflight** request before the real request is allowed.

### 3. The Hack Test (Client vs Server Cookies)
- Backend sets **two cookies**:
  - A normal cookie
  - An `HttpOnly` cookie
- Click the **"Hack Me"** button → runs `alert(document.cookie)`
- Result: You can only see the normal cookie. The `HttpOnly` cookie is completely invisible to JavaScript.

---

## 🛠️ Tech Stack

| Part              | Technology                       | Port |
|-------------------|----------------------------------|------|
| Frontend Server   | Node.js + Express (or live-server) | 3000 |
| Backend API       | Node.js + Express                | 5000 |
| Frontend Code     | HTML + Vanilla JS                | —    |

---

## 📂 Project Structure

```text
split-personality/
│
├── frontend/                 # Origin A (Port 3000)
│   ├── index.html            # Two buttons: "Set Cookie" & "Hack Me"
│   ├── script.js
│   └── server.js             # Simple static server
│
├── backend/                  # Origin B (Port 5000)
│   ├── server.js             # API + cookie setting + CORS config
│   └── package.json
│
└── README.md
