# Nikhil Reddy Levaku

**Java Backend Engineer • Distributed Systems • Concurrency & State Safety**

[Portfolio](https://nikhilreddy810.github.io/portfolio/) &nbsp;•&nbsp; [LinkedIn](https://www.linkedin.com/in/nikhilreddylevaku/) &nbsp;•&nbsp; [Email](mailto:levakunikhilreddy8@gmail.com) &nbsp;•&nbsp; [Resume](https://nikhilreddy810.github.io/portfolio/resume.pdf)

---

## ⚡ Runtime Snapshot

```yaml
engineer: "Nikhil Reddy Levaku"
specialization: "High-Throughput Backend & Distributed State Safety"
production_throughput: "100+ REST APIs shipped in Spring Boot"
cache_efficiency: "40% database query offload via Redis"
concurrency_guarantee: "Pessimistic row locks + idempotency keys (Zero double-charges)"
core_stack: [Java 21, Spring Boot 3.x, PostgreSQL, Redis, Docker, AWS]
```

---

## 🔬 Systems Architecture & Failure Modes

How core engineering challenges were resolved across production and flagship projects:

```
                  ┌───────────────────────────────────────────────────────────┐
                  │                 INCOMING REQUEST WORKLOAD                 │
                  │   [ Concurrent Booking Requests ]    [ Payment Webhook ]  │
                  └─────────────────────────────┬─────────────────────────────┘
                                                │
                                                ▼
                         ┌─────────────────────────────────────────┐
                         │   Spring Security (Stateless JWT/RBAC)  │
                         └──────────────────────┬──────────────────┘
                                                │
                 ┌──────────────────────────────┴──────────────────────────────┐
                 ▼                                                             ▼
   ┌───────────────────────────┐                                 ┌───────────────────────────┐
   │    HIGH CONCURRENCY LOCK  │                                 │     IDEMPOTENCY GUARD     │
   │ Flight Booking System     │                                 │ DeepLure B2B Services     │
   │                           │                                 │                           │
   │ THREAT: Seat Overbooking  │                                 │ THREAT: Duplicate Billing │
   │ SOLUTION:                 │                                 │ SOLUTION:                 │
   │ • PESSIMISTIC_WRITE locks │                                 │ • Redis SETNX + Key TTL   │
   │ • @Transactional Rollback │                                 │ • Atomic wallet mutate    │
   │ • Zero inventory drift    │                                 │ • Zero double charges     │
   └─────────────┬─────────────┘                                 └─────────────┬─────────────┘
                 │                                                             │
                 └──────────────────────────────┬──────────────────────────────┘
                                                │
                                                ▼
                                 ┌─────────────────────────────┐
                                 │   REDIS ASYNC CACHE & WORK  │
                                 │ • Sub-ms search cache hits  │
                                 │ • Async order expiry queue  │
                                 │ • ~40% DB load reduction    │
                                 └──────────────┬──────────────┘
                                                │
                                                ▼
                                 ┌─────────────────────────────┐
                                 │    PERSISTENCE & SCHEMAS    │
                                 │ • PostgreSQL / MySQL        │
                                 │ • Flyway version migrations │
                                 │ • Normalized entity graphs  │
                                 └─────────────────────────────┘
```

---

## 🗂️ Engineering Logbook

<table>
<tr>
<th width="35%">Subsystem / Project</th>
<th width="20%">Stack</th>
<th width="45%">Technical Outcome & Invariant</th>
</tr>

<tr>
<td>
<b>Flight Booking Engine</b><br/>
<sub>Distributed Reservation Core</sub><br/>
<a href="https://github.com/Nikhilreddy810/Flight_Booking"><code>/Flight_Booking</code></a>
</td>
<td>
<code>Spring Boot</code><br/>
<code>MySQL</code><br/>
<code>Redis</code><br/>
<code>Docker</code>
</td>
<td>
<b>Invariant: No seat sold twice under parallel bursts.</b><br/>
Enforced with row-level pessimistic write locking (<code>PESSIMISTIC_WRITE</code>) and transactional rollback on cancellation. Redis caching delivers sub-millisecond query returns.
</td>
</tr>

<tr>
<td>
<b>DeepLure Research Platform</b><br/>
<sub>Production B2B & On-Demand APIs</sub>
</td>
<td>
<code>Java 21</code><br/>
<code>PostgreSQL</code><br/>
<code>Razorpay</code><br/>
<code>Redis</code>
</td>
<td>
<b>Invariant: Strictly idempotent transactions &amp; low latency.</b><br/>
Delivered 100+ production REST APIs. Razorpay webhooks protected with idempotency keys and locks. Redis async queues reduced DB query strain by <b>~40%</b>.
</td>
</tr>

<tr>
<td>
<b>Identity Service</b><br/>
<sub>Enterprise User Management</sub><br/>
<a href="https://github.com/Nikhilreddy810/User_Management"><code>/User_Management</code></a>
</td>
<td>
<code>Spring Boot</code><br/>
<code>Hibernate/JPA</code><br/>
<code>MySQL</code>
</td>
<td>
<b>Invariant: Normalized relational integrity.</b><br/>
Modeled 6-table normalized schema with bidirectional JPA entity mappings, dynamic query predicates, and RFC-7807 problem details.
</td>
</tr>
</table>

---

## 🧰 Technical Competencies

```
LAYER              COMPONENTS
────────────────────────────────────────────────────────────────────────────────
Languages & Core │ Java (17/21), Core Java (Streams, Concurrency, OOP), SQL
Frameworks       │ Spring Boot 3.x, Spring Security (JWT, RBAC), Spring Data JPA, Hibernate
Data & Cache     │ PostgreSQL, MySQL, Redis (Cache-Aside, Async Queues), Flyway Migrations
Systems Design   │ Concurrency Locks, Idempotency Primitives, ACID Isolation, WebSocket/STOMP
Cloud & DevOps   │ Docker, AWS (EC2, S3, RDS), Oracle Cloud (OCI), Linux, Git, CI/CD
Testing & Tools  │ JUnit 5, Mockito, Swagger OpenAPI 3.0, Postman, Maven, Gradle
```

---

## ⏱️ Systems Timeline

```text
2022  ───►  [ SVCE Tirupati ] B.Tech in ECE (CGPA: 8.5/10)
2024  ───►  [ Core Systems  ] Architected 6-table relational JPA Identity Microservice
2025  ───►  [ Cloud & Data  ] SmartBridge Data Intern (Tableau) • OCI Cloud Associate Certified
2026  ───►  [ Concurrency   ] Built Flight Booking Engine (Pessimistic Locks & Redis Caching)
2026  ───►  [ Production    ] Shipped 100+ production APIs at DeepLure Research (Razorpay + Redis)
2026  ───►  [ Selections    ] Extended offers: Axlero Solutions, Infotact Solutions & Global Future Career
NOW   ───►  [ Scale Focus   ] Distributed architectures, event streaming, and cloud resilience
```

---

## 📡 Live Telemetry

<div align="center">

<img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Nikhilreddy810&theme=tokyonight" alt="GitHub Profile Details" />

<br/>

<img width="95%" src="https://github-readme-streak-stats.herokuapp.com/?user=Nikhilreddy810&theme=tokyonight&hide_border=true" alt="GitHub Streak Stats" />

<br/><br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Nikhilreddy810/Nikhilreddy810/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Nikhilreddy810/Nikhilreddy810/output/github-contribution-grid-snake.svg">
  <img alt="GitHub contribution animation" src="https://raw.githubusercontent.com/Nikhilreddy810/Nikhilreddy810/output/github-contribution-grid-snake-dark.svg" width="95%">
</picture>

</div>

---

## 📬 Connect

```text
Portfolio  →  https://nikhilreddy810.github.io/portfolio/
LinkedIn   →  https://www.linkedin.com/in/nikhilreddylevaku/
GitHub     →  https://github.com/Nikhilreddy810
Email      →  levakunikhilreddy8@gmail.com
```

<div align="center">
  <code>architect → implement → optimize → scale</code>
</div>
