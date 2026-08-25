# Sunny Kr Singh

**Backend developer.** I build REST APIs in Java and Spring Boot — authentication, data modelling,
caching, and payments.

Bengaluru, India · **[thesunnycode.me](https://thesunnycode.me)**

```http
GET /sunny HTTP/1.1
Accept: application/json
```

```json
{
  "role":      "Software Engineer (Backend) @ Redalis — part-time",
  "studying":  "MCA @ Jain (Deemed-to-be University)",
  "core":      ["Java 17", "Spring Boot 3", "Spring Security", "JPA / Hibernate"],
  "databases": ["MySQL", "PostgreSQL"],
  "status":    "open to full-time backend roles",
  "reachable": "linkedin.com/in/thesunnycode"
}
```

---

## Endpoints

| Method | Resource | Returns |
|---|---|---|
| `GET` | **[/projects/ecommerce-rest-api](https://github.com/thesunnycode/ecommerce-rest-api)** | Spring Boot API — 24 endpoints, JWT, Stripe |
| `GET` | **[/projects/android-lab](https://github.com/thesunnycode/android-lab)** | Kotlin + Jetpack Compose coursework |
| `GET` | **[/site](https://thesunnycode.me)** | `301 → thesunnycode.me` |
| `GET` | **[/leetcode](https://leetcode.com/u/thesunnycode)** | Problem-solving practice |
| `POST` | **[/contact](mailto:sunnyks058@gmail.com)** | `202 Accepted` — usually within a day |

---

## `GET /projects/ecommerce-rest-api`

A production-oriented e-commerce backend. **24 REST endpoints across 6 modules**, on a normalized
**10-table MySQL schema** managed by Flyway migrations.

**What's in it**

- Stateless **JWT** auth — 15-minute access token, 7-day refresh token in an `HttpOnly`, `Secure`,
  path-scoped cookie. **BCrypt** password hashing
- Role-based authorization, deny-by-default, composed from per-feature rule classes rather than one
  central config
- **Stripe Checkout** behind a `PaymentGateway` interface — one class touches the Stripe SDK, so
  the provider is swappable and the service is testable without network calls
- Payment confirmed asynchronously by **webhook, with HMAC signature verification** against the raw
  request body

**Two decisions I'd defend in an interview**

> `order_items` stores `unit_price` even though `products.price` exists. Without that snapshot,
> changing a product's price silently rewrites the value of every historical order — and a
> customer's invoice stops matching what they paid. **Normalize current state; snapshot historical
> records.**

> Cart IDs are `UUID`s while everything else is auto-increment. Cart IDs are handed to anonymous
> clients, so sequential integers would let anyone walk other people's carts. The UUID *is* the
> authorization.

`Java 17` `Spring Boot 3` `Spring Security` `JPA/Hibernate` `MySQL` `Flyway` `MapStruct` `Stripe` `OpenAPI`

---

## `GET /now`

- Writing **tests properly** — JUnit 5, Mockito, and Testcontainers for integration tests against
  real MySQL. It's the weakest part of my work and the thing I'm fixing first
- **System design** fundamentals: cache invalidation, idempotent endpoints, and scaling read-heavy
  APIs
- **DSA** consistently, rather than only before interviews

---

## `GET /stack`

| | |
|---|---|
| **Core** | Java 17 · Spring Boot 3 · Spring Security · Spring MVC · Spring Data JPA · Hibernate |
| **Data** | MySQL · PostgreSQL · Flyway · Redis |
| **Tooling** | Git · Maven · Postman · IntelliJ IDEA · OpenAPI/Swagger · MapStruct · Stripe |
| **Also shipped with** | Node.js · Express · Prisma · Zod · TypeScript |

I've worked across two backend stacks — Java/Spring and Node/Express. The framework changes; where
you validate input, how you model data, and what you cache don't.

---

## `POST /contact`

[![Website](https://img.shields.io/badge/Website-thesunnycode.me-2f6feb?style=flat-square)](https://thesunnycode.me)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-thesunnycode-0a66c2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/thesunnycode)
[![LeetCode](https://img.shields.io/badge/LeetCode-thesunnycode-f89f1b?style=flat-square&logo=leetcode&logoColor=white)](https://leetcode.com/u/thesunnycode)
[![Email](https://img.shields.io/badge/Email-sunnyks058@gmail.com-ea4335?style=flat-square&logo=gmail&logoColor=white)](mailto:sunnyks058@gmail.com)

<sub><code>429 Too Many Requests</code> — I reply to recruiters faster than that, I promise.</sub>
