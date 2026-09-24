
---

### Project 2: Token Locker

```markdown
# 🔐 Token Locker
### JWT Authentication & CSRF Awareness

> A minimal login system that generates JWTs so you can deeply understand how stateless authentication works — and the security trade-offs of where you store the token.

![Status](https://img.shields.io/badge/Status-Educational%20Project-blue?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-JWT%20%7C%20Auth%20%7C%20CSRF-orange?style=for-the-badge)
![Stack](https://img.shields.io/badge/Stack-Node.js%20%7C%20Express%20%7C%20JWT-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📌 About The Project

This project implements a very simple login system:

- Username: `admin`
- Password: `123`

If the credentials are correct, the server generates a **JWT (JSON Web Token)**.

The goal is **not** to build a full production app — it is to experiment with how JWTs work and the security implications of different storage methods.

---

## 🎯 Learning Goals

- Understand that JWTs are **signed**, not encrypted
- See the full structure of a JWT (Header.Payload.Signature)
- Learn the difference between storing tokens in `localStorage` vs `HttpOnly` cookies
- Understand the XSS vs CSRF trade-off
- Practice protecting routes with JWT verification

---

## 🧪 Experiments

### 1. Deconstruct the Token
Copy the generated JWT and paste it into [jwt.io](https://jwt.io).  
→ You will see that anyone can read the payload (username, role, etc.).  
The signature only proves it hasn’t been tampered with.

### 2. Test Two Storage Approaches

**Approach A – localStorage + Authorization Header**
- Store the JWT in `localStorage`
- Send it as `Authorization: Bearer <token>`
- ✅ Easy to use
- ❌ Vulnerable to XSS (any malicious script can steal the token)

**Approach B – HttpOnly + Secure Cookie**
- Server sets the JWT as an `HttpOnly` cookie
- Browser automatically sends it with requests
- ✅ Protected against XSS
- ❌ Vulnerable to CSRF (needs extra protection like SameSite or CSRF tokens)

Build a protected route (`/dashboard`) and test both methods.

---

## 🛠️ Tech Stack

| Part           | Technology                |
|----------------|---------------------------|
| Backend        | Node.js + Express         |
| Authentication | `jsonwebtoken` library    |
| Frontend       | HTML + Vanilla JS         |
| Cookie parsing | `cookie-parser` (optional)|

---

## 📂 Project Structure

```text
token-locker/
│
├── backend/
│   ├── server.js             # Login route + protected route
│   ├── auth.js               # JWT sign & verify helpers
│   └── package.json
│
├── frontend/
│   ├── index.html            # Login form
│   ├── dashboard.html        # Protected page
│   └── script.js
│
└── README.md
