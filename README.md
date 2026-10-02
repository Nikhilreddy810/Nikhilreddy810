# Nikhil Reddy Levaku

**DevOps-Focused Backend Engineer • Cloud Infrastructure • Distributed Systems**

[Portfolio](https://nikhilreddy810.github.io/portfolio/) &nbsp;•&nbsp; [LinkedIn](https://www.linkedin.com/in/nikhilreddylevaku/) &nbsp;•&nbsp; [Email](mailto:levakunikhilreddy8@gmail.com) &nbsp;•&nbsp; [Resume](https://nikhilreddy810.github.io/portfolio/resume.pdf)

---

## ⚡ Runtime Snapshot

```yaml
engineer: "Nikhil Reddy Levaku"
specialization: "DevOps & Cloud CI/CD • High-Throughput Java Backend"
cicd_automation: "GitHub Actions: build, test, Docker Hub push, automated AWS EC2 deploy"
containerization: "Docker & Docker Compose (Spring Boot, PostgreSQL, Redis)"
cloud_infrastructure: "AWS (EC2, VPC, Security Groups, S3, EBS, IAM, Auto Scaling) & Linux"
production_throughput: "100+ REST APIs delivered in Spring Boot across B2B platforms"
cache_efficiency: "40% database query offload via Redis worker queues"
concurrency_guarantee: "Pessimistic row locks + idempotency keys (Zero double-charges)"
core_stack: [Java 21, Spring Boot 3.x, Docker, Docker Compose, GitHub Actions, AWS EC2, PostgreSQL, Redis]
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
<th width="25%">Stack</th>
<th width="40%">Technical Outcome & Invariant</th>
</tr>

<tr>
<td>
<b>Flight Booking Engine &amp; CI/CD</b><br/>
<sub>Containerized Reservation Platform</sub><br/>
<a href="https://github.com/Nikhilreddy810/Flight_Booking"><code>/Flight_Booking</code></a>
</td>
<td>
<code>Spring Boot</code><br/>
<code>PostgreSQL</code><br/>
<code>Redis</code><br/>
<code>Docker Compose</code><br/>
<code>GitHub Actions</code><br/>
<code>AWS EC2</code>
</td>
<td>
<b>Invariant: Automated zero-downtime deployment &amp; concurrency safety.</b><br/>
Containerized with Docker Compose. Built a full GitHub Actions CI/CD pipeline (Gradle build/test, Docker Hub push, automated SSH deploy to AWS EC2 via <code>docker compose up -d</code>). Resolved Flyway MySQL syntax migration failure. Concurrency-safe seat reservation with pessimistic locks (<code>PESSIMISTIC_WRITE</code>) and transactional rollbacks.
</td>
</tr>

<tr>
<td>
<b>DeepLure Research Platform</b><br/>
<sub>Production B2B & On-Demand APIs (May 2026 – Aug 2026)</sub>
</td>
<td>
<code>Java 21</code><br/>
<code>PostgreSQL</code><br/>
<code>Redis</code><br/>
<code>AWS S3</code><br/>
<code>Razorpay</code>
</td>
<td>
<b>Invariant: Strictly idempotent transactions &amp; secure media pipeline.</b><br/>
Delivered 100+ production REST APIs. Razorpay webhooks protected with idempotency keys and locks. AWS S3 storage pipeline with pre-signed URLs for secure media lifecycle. Redis async queues reduced DB load by <b>~40%</b>.
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
Cloud & DevOps   │ Linux, Networking, AWS (IAM, EC2, VPC, Security Groups, S3, EBS, Auto Scaling)
Containers & CI  │ Docker, Docker Compose, GitHub Actions (CI/CD), Docker Hub, Git
Languages & Core │ Java, SQL, Core Java (Streams, Concurrency, OOP), Bash
Frameworks       │ Spring Boot, Spring Security (JWT, RBAC), Spring Data JPA, Hibernate
Databases & Cache│ PostgreSQL, MySQL, Redis (Cache-Aside, Async Queues), Flyway Migrations
Systems Design   │ REST API Design, Concurrency Locks, Idempotency, Transaction Isolation (ACID)
Testing & Tools  │ JUnit 5, Mockito, Swagger / OpenAPI, Postman, Gradle, Maven
```

---

## ⏱️ Systems Timeline

```text
2022  ───►  [ SVCE Tirupati ] B.Tech in ECE (CGPA: 8.5/10)
2024  ───►  [ Core Systems  ] Architected 6-table relational JPA Identity Microservice
2025  ───►  [ Cloud & Data  ] SmartBridge Data Intern (Tableau) • OCI Cloud Associate Certified
2026  ───►  [ Concurrency   ] Built Flight Booking Engine (Pessimistic Locks & Redis Caching)
2026  ───►  [ DevOps CI/CD  ] Automated GitHub Actions CI/CD pipeline & Docker Compose deploy to AWS EC2
2026  ───►  [ Production    ] Shipped 100+ production APIs at DeepLure Research (Razorpay + Redis)
2026  ───►  [ Selections    ] Extended offers: Axlero Solutions, Infotact Solutions & Global Future Career
NOW   ───►  [ Scale Focus   ] Cloud infrastructure automation, event-driven architectures, and distributed systems
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
