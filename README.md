<p align="center">
  <img src="./backend/assets/sci-scope-banner.png" alt="SciScope Banner" width=700"/>
</p>
<p align="center"><em>Curated science news for educators — fast, filterable, and bookmarkable.</em></p>

<p align="center">
  <img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build Passing"/>
  <img src="https://img.shields.io/badge/coverage-80%25-yellow" alt="Coverage 80%"/>
  <img src="https://img.shields.io/badge/made%20with-%E2%98%95%EF%B8%8F%20coffee-blue" alt="Made with Coffee"/>
  <img src="https://img.shields.io/badge/made%20with-%F0%9F%92%9C%20love-ff69b4" alt="Made with Love"/>
</p>

# 🔬 SciScope

**SciScope** is a backend API for browsing, searching, and saving science news. It integrates with an external news API and adds structured bookmarking, grouping, caching, and analytics on top. It was built as a backend-focused project to demonstrate API design, data modeling, and reliability concerns that show up in real-world systems.

---

## ✨ What SciScope Does

* Fetches and caches current science news from an external API
* Supports keyword search and pagination
* Allows users to bookmark articles and organize them into groups
* Exposes analytics endpoints (e.g. most-bookmarked articles, most-active users)
* Separates concerns cleanly across routes, controllers, services, and models

This project is intentionally backend-only and focuses on correctness, structure, and observability rather than UI polish.

---

## 🧱 Architecture Highlights

* **Modular API design** with clear separation between routing, business logic, and persistence
* **External API integration with caching** to reduce redundant requests and improve response time
* **Relational data modeling** using PostgreSQL and Objection.js
* **Analytics queries** implemented with a mix of ORM and raw SQL
* **Centralized error handling and logging** for predictable failures
* **Pagination and sorting** implemented consistently across endpoints

---

## 🧪 Testing & Reliability

SciScope includes unit, integration, and API-level tests that cover:

* External API failure handling
* Auth-protected routes
* Pagination edge cases
* Caching behavior
* Analytics queries

Tests are written with **Jest** and **Supertest**, and run against a local PostgreSQL instance.

---

## 📦 Tech Stack

* **Node.js**, **Express**
* **PostgreSQL**, **Knex.js**, **Objection.js**
* **Jest** + **Supertest** for testing
* **node-cache** for in-memory caching
* **Axios** for external API requests

---

## 🚀 Setup (Local)

```bash
git clone https://github.com/your-username/sciscope.git
cd sciscope
npm install
cp .env.example .env
# add NEWS_API_KEY, database credentials, JWT_SECRET
npm run migrate
npm run seed
npm run start
```

---

## 📍 Selected Endpoints

### Articles

* `GET /api/v1/news` – Trending science news
* `GET /api/v1/search?keyword=` – Keyword search

### Bookmarks

* `POST /api/v1/bookmarks`
* `GET /api/v1/bookmarks`
* `DELETE /api/v1/bookmarks/:id`

### Bookmark Groups

* `POST /api/v1/bookmark-groups`
* `PATCH /api/v1/bookmark-groups/:id`
* `DELETE /api/v1/bookmark-groups/:id`

### Analytics

* `GET /api/v1/analytics/most-bookmarked-articles`
* `GET /api/v1/analytics/top-bookmarking-users`

---

## 🧠 Design Notes

* This project uses **Objection.js** for most queries and **raw SQL** where it improves clarity or performance.
* Caching is applied at the service layer, not the controller layer.
* Analytics endpoints are currently public and may be protected in future iterations.

---

## 🔮 Future Improvements

* PostgreSQL full-text search
* Auth protection for analytics routes
* Frontend client for browsing and bookmarking
* Deployment and monitoring

---

## 👩🏽‍💻 Author

Tamara Dowis
[GitHub](https://github.com/tamara-builds) | [LinkedIn](https://www.linkedin.com/in/tamara-dowis/)
