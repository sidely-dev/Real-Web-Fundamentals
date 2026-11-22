
# 🌐 Real-Web-Fundamentals

> A hands-on collection of small projects built to understand how the web and networks actually work — from packets and DNS to cookies, JWTs, performance, and encryption.

![Status](https://img.shields.io/badge/Status-Active-blue?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Networking%20%7C%20Web%20Security%20%7C%20Performance-orange?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Educational%20Projects-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📌 About This Repository

**Real-Web-Fundamentals** is a learning lab focused on the technical foundations of the web and the internet.

Instead of only reading theory, each project is built to make a specific concept visible and understandable by constructing it (or breaking it) hands-on.

The goal is to close the gap between:
- Knowing the high-level idea of how the web works
- Actually understanding how data moves, what is exposed, and how common web mechanisms behave

---

## 🧠 Learning Philosophy

- Build small, focused projects
- Prefer clarity over complexity
- Make abstract concepts visible
- Write clear explanations after building
- Learn by observing real behavior (and real problems)

---

## 🚀 Current Projects

### Networking Fundamentals
| Project | Description |
|---------|-------------|
| [Packet Journey Visualizer](./Packet%20Journey%20Visualizer) | Visualizes how a packet travels from your device to a destination |
| [DNS Resolution Demo](./DNS%20Resolution%20Demo) | Shows the step-by-step process of turning a domain name into an IP address |
| [Mini Client–Server Chat](./Mini%20Client–Server%20Chat) | Basic TCP chat to understand sockets, ports, and client-server communication |
| [Local Port & Service Mapper](./Local%20Port%20%26%20Service%20Mapper) | Scans your own machine for open ports and explains common services |
| [HTTP vs HTTPS Comparison](./HTTP%20vs%20HTTPS%20Comparison) | Side-by-side demo of what is visible with and without encryption |

### Web Security & Browser Behavior
| Project | Description |
|---------|-------------|
| [The "Split-Personality" Web App](./The%20Split-Personality%20Web%20App) | Demonstrates CORS and the difference between normal cookies and HttpOnly cookies |
| [The "Token Locker"](./The%20Token%20Locker) | Explores JWT authentication and the trade-offs of different token storage methods |

### Web Performance
| Project | Description |
|---------|-------------|
| [The "Laggy Blog" Dashboard](./The%20Laggy%20Blog%20Dashboard) | Intentionally breaks Core Web Vitals (CLS, TTFB/LCP, FID) and then fixes them |

---

## 🛠️ Typical Tech Stack

Most projects use simple, transparent tools:

- HTML, CSS, JavaScript
- Python or Java (for networking tools)
- Node.js + Express (for small backend demos)
- Browser DevTools and basic system tools

The focus is on understanding, not on using the most advanced frameworks.

---

## 📂 Repository Structure

```text
Real-Web-Fundamentals/
│
├── Packet Journey Visualizer/
├── DNS Resolution Demo/
├── Mini Client–Server Chat/
├── Local Port & Service Mapper/
├── HTTP vs HTTPS Comparison/
├── The Split-Personality Web App/
├── The Token Locker/
├── The Laggy Blog Dashboard/
│
└── README.md
