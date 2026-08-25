<h1 align="center">Sunny Kr Singh</h1>

<p align="center">
  I build <b>REST APIs</b> in Java and Spring Boot — authentication, data modelling, caching, and payments.
</p>

<p align="center">
  Backend engineer at <b>Redalis</b> · MCA @ Jain University · Bengaluru, India
</p>

<p align="center">
  <a href="https://thesunnycode.me">Website</a> ·
  <a href="https://linkedin.com/in/thesunnycode">LinkedIn</a> ·
  <a href="https://leetcode.com/u/thesunnycode">LeetCode</a> ·
  <a href="mailto:sunnyks058@gmail.com">Email</a>
</p>

<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=java,spring,hibernate,mysql,postgres,redis,maven,git,postman,idea&perline=10" alt="Java, Spring, Hibernate, MySQL, PostgreSQL, Redis, Maven, Git, Postman, IntelliJ IDEA" />
  </a>
</p>

<br>

## E-Commerce REST API

<table>
<tr>
<td align="center"><b>24</b><br><sub>endpoints</sub></td>
<td align="center"><b>6</b><br><sub>modules</sub></td>
<td align="center"><b>10</b><br><sub>tables</sub></td>
<td align="center"><b>5</b><br><sub>migrations</sub></td>
<td align="center"><b>15m / 7d</b><br><sub>token lifetimes</sub></td>
</tr>
</table>

The backend for an online store — accounts, a product catalog, shopping carts, orders, and real
card payments.

**What it does**

- Customers register, log in, browse products by category, and build a cart
- Checkout creates an order and hands the customer to Stripe to pay by card
- Admins manage the catalog; customers only ever see their own orders

**How it works**

- **Login** issues two tokens — a short one used on every request, and a longer one kept in a
  cookie that JavaScript can't read. If the short one leaks, it expires in minutes. Passwords are
  hashed with BCrypt, never stored.
- **Every endpoint is locked by default.** Access has to be granted explicitly, so a new endpoint
  is never accidentally left open. Each module declares its own rules instead of one giant config
  file.
- **Card details never touch the server.** Stripe hosts the payment page, then tells the API the
  result through a webhook. That webhook is signature-checked, so nobody can fake a "payment
  succeeded" message.
- **Orders remember their own prices.** Each line stores what the item cost at the moment of
  purchase — so changing a price later can't rewrite what past customers paid.
- **Cart IDs are random UUIDs**, because you can shop without an account. A guessable number would
  let anyone open someone else's cart.

Built with Flyway migrations so the database schema is version-controlled alongside the code.

<a href="https://github.com/thesunnycode/ecommerce-rest-api"><b>→ Read the code</b></a>

<br>

## Currently

**Writing tests properly** — JUnit 5, Mockito, and Testcontainers against real MySQL. It's the
weakest part of my work and the thing I'm fixing first.

**System design fundamentals** — cache invalidation, idempotent endpoints, and scaling read-heavy
APIs.

**DSA, consistently** — rather than only before interviews.

<br>

## Stack

**Core** — Java 17 · Spring Boot 3 · Spring Security · Spring MVC · Spring Data JPA · Hibernate

**Data** — MySQL · PostgreSQL · Flyway · Redis

**Tooling** — Git · Maven · Postman · IntelliJ IDEA · OpenAPI/Swagger · MapStruct · Stripe

**Also shipped with**

<img src="https://skillicons.dev/icons?i=js,ts,nodejs,express,prisma,kotlin,androidstudio&perline=7" alt="JavaScript, TypeScript, Node.js, Express, Prisma, Kotlin, Android Studio" height="42" />

I've worked across two backend stacks. The framework changes; where you validate input, how you
model data, and what you cache don't.

<br>

---

<p align="center">
  <sub>Open to full-time backend engineering roles.</sub>
</p>
