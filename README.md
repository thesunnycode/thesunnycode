# Sunny Kr Singh

I build REST APIs in Java and Spring Boot — authentication, data modelling, caching, and payments.

Backend engineer at **Redalis** (part-time) while finishing my **MCA** at Jain University.
Bengaluru, India · [thesunnycode.me](https://thesunnycode.me)

---

## E-Commerce REST API

**[github.com/thesunnycode/ecommerce-rest-api](https://github.com/thesunnycode/ecommerce-rest-api)**

A production-oriented e-commerce backend — 24 REST endpoints across 6 modules, on a normalized
10-table MySQL schema managed by Flyway migrations.

Stateless JWT authentication with a 15-minute access token and a 7-day refresh token in an
`HttpOnly`, `Secure`, path-scoped cookie. BCrypt password hashing. Deny-by-default authorization
composed from per-feature rule classes rather than one central config. Stripe Checkout behind a
`PaymentGateway` interface, with payment confirmed asynchronously by webhook and verified against
the raw request body's HMAC signature.

**Two decisions I'd defend in a review:**

`order_items` stores `unit_price` even though `products.price` already exists. Without that
snapshot, changing a product's price silently rewrites the value of every historical order, and a
customer's invoice stops matching what they actually paid. Normalize current state; snapshot
historical records.

Cart IDs are UUIDs while everything else is auto-increment. Cart IDs are handed to anonymous
clients, so sequential integers would let anyone walk other people's carts. The UUID *is* the
authorization.

`Java 17` · `Spring Boot 3` · `Spring Security` · `JPA/Hibernate` · `MySQL` · `Flyway` ·
`MapStruct` · `Stripe` · `OpenAPI`

---

## Currently

Writing tests properly — JUnit 5, Mockito, and Testcontainers against real MySQL. It's the weakest
part of my work and the thing I'm fixing first.

Working through system design fundamentals: cache invalidation, idempotent endpoints, and scaling
read-heavy APIs.

Practising data structures and algorithms consistently, rather than only before interviews.

---

## Stack

**Core** — Java 17, Spring Boot 3, Spring Security, Spring MVC, Spring Data JPA, Hibernate
**Data** — MySQL, PostgreSQL, Flyway, Redis
**Tooling** — Git, Maven, Postman, IntelliJ IDEA, OpenAPI/Swagger, MapStruct, Stripe
**Also shipped with** — Node.js, Express, Prisma, Zod, TypeScript

I've worked across two backend stacks. The framework changes; where you validate input, how you
model data, and what you cache don't.

---

## Elsewhere

[thesunnycode.me](https://thesunnycode.me) ·
[LinkedIn](https://linkedin.com/in/thesunnycode) ·
[LeetCode](https://leetcode.com/u/thesunnycode) ·
[sunnyks058@gmail.com](mailto:sunnyks058@gmail.com)

Open to full-time backend engineering roles.
