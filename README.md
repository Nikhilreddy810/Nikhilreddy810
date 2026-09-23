# Nikhil Reddy Levaku

**Java Backend Engineer • Distributed Systems • High-Concurrency Architecture**

Building resilient backend microservices, transactional workflows, and distributed infrastructure with Core Java, Spring Boot, PostgreSQL, and Redis.

[Portfolio](https://nikhilreddy810.github.io/portfolio/) &nbsp;•&nbsp; [LinkedIn](https://www.linkedin.com/in/nikhilreddylevaku/) &nbsp;•&nbsp; [Email](mailto:levakunikhilreddy8@gmail.com) &nbsp;•&nbsp; [Resume](https://nikhilreddy810.github.io/portfolio/resume.pdf)

---

## / engineering-specs

```java
public record SystemArchitect(
    String engineer,
    String primaryDomain,
    List<String> coreStack,
    List<String> concurrencyPatterns
) {
    public static final SystemArchitect PROFILE = new SystemArchitect(
        "Nikhil Reddy Levaku",
        "High-Throughput Backend & Distributed Transactions",
        List.of("Java 17/21", "Spring Boot 3.x", "PostgreSQL", "Redis", "Docker"),
        List.of("Idempotent API Design", "Pessimistic & Optimistic Locking", "ACID Rollbacks", "Redis Worker Queues")
    );
}
```

```
┌── Backend Systems ─────────────────────────────────────────────────────────────┐
│ Java (17/21) • Spring Boot 3.x • REST APIs • Spring Security (JWT/RBAC)        │
│ Layered architecture (Controller → Service → Repository), DTO validation       │
└────────────────────────────────────────────────────────────────────────────────┘

┌── Data & Distributed State ────────────────────────────────────────────────────┐
│ PostgreSQL • MySQL • Redis (In-Memory Cache & Asynchronous Workers) • Flyway   │
│ Optimistic/pessimistic row locking, 40% DB load reduction, transactional isolation ┘
└────────────────────────────────────────────────────────────────────────────────┘

┌── Cloud, DevOps & Quality ─────────────────────────────────────────────────────┐
│ Docker • AWS (EC2, S3, RDS) • Linux • Git & CI/CD • JUnit 5 • Mockito • OpenAPI│
│ Multi-stage container builds, automated unit/integration testing, Swagger UI   │
└────────────────────────────────────────────────────────────────────────────────┘
```

---

## / system-architecture-patterns

### Distributed Concurrency & Idempotency Pipeline

```
[ Client / Webhook ] ──( HTTPS + JWT Token )──> [ Spring Boot API Gateway ]
                                                       │
                                  ┌────────────────────┴────────────────────┐
                                  ▼                                         ▼
                      [ Request Idempotency Key ]               [ Hibernate / JPA Entity ]
                      • Redis GET/SETNX with TTL                • Optimistic versioning check (@Version)
                      • Prevents duplicate mutations            • Pessimistic write lock (PESSIMISTIC_WRITE)
                                  │                                         │
                                  └────────────────────┬────────────────────┘
                                                       ▼
                                      [ @Transactional Execution Block ]
                                      • Atomic balance & seat status mutations
                                      • Automatic rollback on runtime exception
                                                       │
                                  ┌────────────────────┴────────────────────┐
                                  ▼                                         ▼
                      [ Redis Cache Layer ]                     [ Relational Storage ]
                      • Evict / invalidate stale cache          • PostgreSQL / MySQL commit
                      • Push notification event to Redis queue  • Flyway schema version sync
```

---

## / deep-dive-projects

### ✈️ Flight Booking System — Distributed Reservation Engine
`Spring Boot` • `Java` • `MySQL` • `Redis` • `Docker` • `Swagger OpenAPI` • [View Repository](https://github.com/Nikhilreddy810/Flight_Booking)

- **The Problem:** Simultaneous user bookings during flash sales cause seat race conditions, dirty reads, and inventory drift.
- **Architecture Solution:** 
  - Implemented **concurrency-safe seat allocation with pessimistic row locks** (`PESSIMISTIC_WRITE`) preventing multiple threads from booking the same seat inventory.
  - Wrapped booking and payment workflows inside `@Transactional` boundaries with **declarative rollback**, ensuring atomic recovery if payment or confirmation fails.
  - Layered **Redis caching** for high-frequency flight search endpoints with automatic TTL invalidation, minimizing repetitive database query overhead.
  - Containerized with **Docker** and fully documented with **Swagger UI / OpenAPI 3.0**.

### 💼 Production Microservices & Payment Guardrails — DeepLure Research
`Java 21` • `Spring Boot 3.x` • `PostgreSQL` • `Redis` • `Docker` • `Razorpay`

- **The Problem:** B2B marketplaces face double-billing risks on network retries and database bottlenecks from polling notifications.
- **Architecture Solution:**
  - Designed and delivered **100+ production REST APIs** across authentication, multi-tenant catalog, ordering, and partner modules.
  - Integrated **Razorpay payment webhooks with idempotency keys**, eliminating race conditions and preventing duplicate debits across concurrent requests.
  - Engineered **Redis-backed asynchronous worker queues** for order expiry and notification dispatch, reducing database query load by **~40%**.
  - Built real-time customer and provider chat over **WebSocket / STOMP** paired with Firebase Cloud Messaging (FCM).
  - Maintained schema integrity with **Flyway migrations** and authored automated test suites with **JUnit 5 and Mockito**.

### 👤 Identity & User Management Microservice
`Spring Boot` • `Hibernate / JPA` • `MySQL` • `Postman` • [View Repository](https://github.com/Nikhilreddy810/User_Management)

- **The Problem:** Enterprise services require normalized entity graphs with dynamic filtering without triggering N+1 query problems.
- **Architecture Solution:**
  - Designed a normalized 6-table relational MySQL schema with bidirectional JPA entity mappings.
  - Implemented dynamic multi-field search with parameter validation and centralized exception handling conforming to RFC-7807 problem details.
  - Published and verified complete testing workflows with comprehensive Postman collections.

---

## / technical-matrix

| Domain | Technologies, Standards & Tools |
| :--- | :--- |
| **Backend & Core** | `Java (17, 21)`, `Core Java (OOP, Streams, Concurrency, Generics)`, `SQL`, `RESTful Design` |
| **Frameworks** | `Spring Boot 3.x`, `Spring Security (JWT, RBAC, OAuth2/OTP)`, `Spring Data JPA`, `Hibernate ORM` |
| **Databases & Caching** | `PostgreSQL`, `MySQL`, `Redis (Cache-Aside, Distributed Queues, Pub/Sub)`, `Flyway Migrations` |
| **Distributed Concepts** | `Idempotent API Design`, `Pessimistic & Optimistic Locking`, `Transaction Isolation (ACID)`, `WebSocket / STOMP` |
| **Cloud & DevOps** | `Docker (Multi-stage builds)`, `AWS (EC2, S3, RDS)`, `Oracle Cloud Infrastructure (OCI)`, `Linux CLI`, `Git`, `CI/CD` |
| **Testing & Quality** | `JUnit 5`, `Mockito`, `Postman`, `Swagger / OpenAPI 3.0`, `Maven`, `Gradle` |

---

## / technical-roadmap

```
backend-foundations ──────► [ Core Java 21, Spring Boot 3.x, JPA/Hibernate, PostgreSQL ]
        │
        ▼
distributed-state   ──────► [ Redis Caching, Idempotency Guards, Concurrency Locking ]
        │
        ▼
messaging-tier      ──────► [ WebSocket/STOMP, Apache Kafka Event Streaming ]
        │
        ▼
container-platform  ──────► [ Docker Multi-stage Builds, Containerized Deployments ]
        │
        ▼
cloud-infrastructure─────► [ AWS (EC2/S3/RDS), Oracle Cloud Infrastructure (OCI) ]
        │
        ▼
scalable-systems    ──────► [ Microservices Discovery, Distributed Tracing, High Availability ]
```

---

## / engineering-log

```text
[2022] Began B.Tech in Electronics & Communication at SVCE Tirupati (CGPA: 8.5 / 10)
[2024] Architected User Management System with 6-table normalized relational schema
[2025] Completed Data Analytics Internship at SmartBridge; built 3 Tableau dashboards
[2025] Achieved Oracle Cloud Infrastructure (OCI) Foundations Associate Certification
[2026] Architected Flight Booking System with pessimistic locking, Redis, and transactional rollbacks
[2026] Shipped 100+ production REST APIs at DeepLure Research with Redis, Razorpay, and Docker
[2026] Extended Java Developer selections from Axlero Solutions & Infotact Solutions
[2026] Solved 100+ Data Structures & Algorithms problems on LeetCode
[ACTIVE] Deepening distributed systems architecture, event-driven streaming, and cloud resiliency
```

---

## / live-telemetry

<div align="center">

<img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Nikhilreddy810&theme=tokyonight" alt="GitHub Profile Details" />
<img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Nikhilreddy810&theme=tokyonight" alt="Top Languages by Commits" />

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

## / connect

If you are working on backend engineering, distributed architectures, or high-concurrency systems, let's talk:

- 🌐 **Portfolio:** [nikhilreddy810.github.io/portfolio](https://nikhilreddy810.github.io/portfolio/)
- 💼 **LinkedIn:** [linkedin.com/in/nikhilreddylevaku](https://www.linkedin.com/in/nikhilreddylevaku/)
- 📬 **Email:** [levakunikhilreddy8@gmail.com](mailto:levakunikhilreddy8@gmail.com)
- 🐙 **GitHub:** [github.com/Nikhilreddy810](https://github.com/Nikhilreddy810)

<p align="center">
  <code>architect → implement → optimize → scale</code>
</p>
