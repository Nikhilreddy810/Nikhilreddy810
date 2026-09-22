# Nikhil Reddy Levaku

**Java Backend Developer • Distributed Systems • Spring Boot**

Building reliable backend systems, APIs, and scalable infrastructure.

[Portfolio](https://nikhilreddy810.github.io/portfolio/) &nbsp;•&nbsp; [LinkedIn](https://www.linkedin.com/in/nikhilreddylevaku/) &nbsp;•&nbsp; [Email](mailto:levakunikhilreddy8@gmail.com) &nbsp;•&nbsp; [Resume](https://nikhilreddy810.github.io/portfolio/resume.pdf)

---

## / engineering

```
┌── Backend Engineering ────────────────────────────────────────────────────────┐
│ Java • Spring Boot • REST APIs • JPA/Hibernate • Spring Security (JWT/RBAC)   │
└── Concurrency, transactional consistency, and idempotent service workflows ────┘

┌── Distributed Systems ────────────────────────────────────────────────────────┐
│ Redis (Caching & Queues) • Row-level Locking • Idempotency • Distributed Sync │
└── Cache eviction patterns, query optimization, and latency reduction ─────────┘

┌── Cloud & DevOps ─────────────────────────────────────────────────────────────┐
│ Linux • Docker • AWS • Git • CI/CD Pipelines • Flyway Database Migrations    │
└── Containerized runtime, isolated environments, and structured build workflows ┘

┌── Architecture ───────────────────────────────────────────────────────────────┐
│ Layered Architecture • Microservices • Database Normalization • System Design │
└── Controller-Service-Repository patterns with centralized exception handling ──┘
```

---

## / currently-building

```
backend
   │
   ▼
microservices ──► [Service Discovery & Distributed Config]
   │
   ▼
messaging     ──► [Apache Kafka Event Streaming]
   │
   ▼
containers    ──► [Docker & Multi-stage Builds]
   │
   ▼
cloud         ──► [AWS Core Infrastructure]
   │
   ▼
orchestration ──► [Kubernetes Deployments & Ingress]
   │
   ▼
system design ──► [High Availability & CAP Trade-offs]
```

---

## / featured-projects

### Flight Booking System

`Spring Boot` • `Java` • `MySQL` • `Redis` • `Docker` • `REST API`

A distributed backend booking engine with transactional workflows, pessimistic seat allocation, and zero-inventory-drift guarantees under concurrent traffic.

- **Problem solved:** Eliminates overbooking and race conditions during simultaneous flight seat reservations.
- **Engineering focus:** Pessimistic write locking (`Isolation.SERIALIZABLE`), Redis idempotency key validation with TTL, transactional rollback on cancellation, and layered architecture (Controller → Service → Repository).

→ [Repository](https://github.com/Nikhilreddy810/Flight_Booking)

---

### User Management System

`Spring Boot` • `Java` • `Hibernate/JPA` • `MySQL` • `Postman`

An enterprise-grade identity and user CRUD service with dynamic search criteria, robust payload validation, and centralized exception handling.

- **Problem solved:** Provides clean, decoupled identity management with normalized database schemas.
- **Engineering focus:** 6-table normalized relational schema, JPA relationship mappings, pagination and filtering, and comprehensive Postman collection coverage.

→ [Repository](https://github.com/Nikhilreddy810/User_Management)

---

### Production B2B Services & Async Engine (DeepLure)

`Java 21` • `Spring Boot 3.x` • `PostgreSQL` • `Redis` • `Razorpay` • `Docker`

Production microservices architecture powering multi-tenant order fulfillment, payment verification, and asynchronous event workers.

- **Problem solved:** Handles high-volume marketplace transactions and notifications without database query degradation.
- **Engineering focus:** Shipped 100+ production REST APIs, integrated Razorpay idempotency guards, and engineered Redis background queues that reduced database load by ~40%.

---

## / architecture

A high-level view of the transactional concurrency model in the **Flight Booking System**:

```
[ Client / HTTP Request ]
           │
           ▼
[ Spring Boot REST Controller ] ── (JWT Auth & DTO Validation)
           │
           ▼
[ Service Layer (@Transactional) ]
     │                 │
     ▼                 ▼
[ Redis Template ]  [ MySQL Database ]
  • Idempotency       • Pessimistic Row Lock (PESSIMISTIC_WRITE)
  • 15m Cache TTL     • Atomic Seat Status Commit / Rollback
```

---

## / engineering-experience

### Backend Engineering — DeepLure Research (May 2026 – Present)
- Engineered and shipped **100+ production REST APIs** across B2B marketplace and on-demand services.
- Implemented secure authentication and authorization using **stateless JWT tokens and RBAC**, with OTP verification delivered over SMS and email.
- Integrated **Razorpay payment gateway** with strict idempotency keys and locking primitives to prevent double-charges and race conditions.
- Built **Redis-backed asynchronous workers** for notification delivery, payment reconciliation, and booking expiration, cutting database query load by **~40%**.
- Modeled normalized PostgreSQL schemas using **Hibernate/JPA and versioned Flyway migrations**.

### Data Analytics — SmartBridge / APSCHE (May 2025 – Jul 2025)
- Cleaned and transformed manufacturing and sales datasets utilizing structured **multi-table SQL joins** and aggregate queries.
- Engineered **3 interactive Tableau dashboards** for operational inventory tracking and production bottleneck analysis.

---

## / tech-stack

```
Backend        │ Java (17/21), Spring Boot, Spring Security (JWT/RBAC), Hibernate/JPA, REST APIs
Databases      │ MySQL, PostgreSQL, Redis (Caching & Asynchronous Queues)
Cloud & DevOps │ Linux, Docker, AWS, Git, CI/CD Pipelines, Flyway Migrations
Tooling        │ Maven, Gradle, Postman, Swagger/OpenAPI, JUnit 5, Mockito
```

---

## / selected-work

Some systems and repositories I've built and maintained:

- **[Flight_Booking](https://github.com/Nikhilreddy810/Flight_Booking)** — Distributed seat allocation engine with pessimistic locking, Redis, and Swagger documentation.
- **[User_Management](https://github.com/Nikhilreddy810/User_Management)** — Enterprise user CRUD service built on a 6-table normalized relational MySQL schema with JPA.
- **[grid07-backend-assignment](https://github.com/Nikhilreddy810/grid07-backend-assignment)** — Spring Boot microservice featuring Redis atomic guardrails and notification batching.
- **[portfolio](https://github.com/Nikhilreddy810/portfolio)** — Live engineering portfolio website showcasing system case studies, interactive filters, and architecture diagrams.

*Check the pinned repositories above for full source code and setup guides.*

---

## / engineering-log

```
[2022] Began B.Tech in Electronics & Communication at SVCE Tirupati (CGPA: 8.5 / 10)
[2024] Architected User Management System with 6-table normalized relational schema
[2025] Completed Data Analytics Internship at SmartBridge; built 3 Tableau dashboards
[2025] Achieved Oracle Cloud Infrastructure (OCI) Foundations Associate Certification
[2026] Architected Flight Booking System with pessimistic locking and Redis caching
[2026] Shipped 100+ production REST APIs at DeepLure Research with Redis and Spring Boot
[2026] Extended Java Developer selections from Axlero Solutions & Infotact Solutions
[2026] Expanding active focus into cloud-native microservices, Kafka, and Kubernetes
```

---

## / activity

Recent engineering areas:
- Production REST API development in Spring Boot & PostgreSQL
- Concurrency control, Redis cache layers, and transactional idempotency
- Cloud & DevOps infrastructure: Docker containerization and AWS foundations
- LeetCode problem solving: 100+ Data Structures & Algorithms solved

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Nikhilreddy810&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" height="155" alt="GitHub Stats" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Nikhilreddy810&layout=compact&theme=tokyonight&hide_border=true" height="155" alt="Top Languages" />
</p>

---

## / connect

If you are working on backend systems, distributed architectures, or cloud infrastructure, feel free to connect:

- **Portfolio:** [https://nikhilreddy810.github.io/portfolio/](https://nikhilreddy810.github.io/portfolio/)
- **LinkedIn:** [https://www.linkedin.com/in/nikhilreddylevaku/](https://www.linkedin.com/in/nikhilreddylevaku/)
- **Email:** [levakunikhilreddy8@gmail.com](mailto:levakunikhilreddy8@gmail.com)
- **GitHub:** [https://github.com/Nikhilreddy810](https://github.com/Nikhilreddy810)

---

<p align="center">
  <code>build → learn → design → ship</code>
</p>
