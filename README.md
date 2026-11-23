<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:512BD4,100:1F6FEB&height=170&section=header&text=Tran%20Quang%20Minh&fontSize=44&fontColor=ffffff&fontAlignY=34&desc=Backend%20Developer%20%E2%80%A2%20C%23%20%2F%20.NET&descSize=17&descAlignY=56" width="100%" alt="Tran Quang Minh — Backend Developer" />

**I build backend APIs that stay correct under load: multi-tenant SaaS, concurrency-safe booking, and real-time systems.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-hitech2605-0A66C2?style=for-the-badge)](https://linkedin.com/in/hitech2605)
[![Email](https://img.shields.io/badge/Email-minhtq.2605%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:minhtq.2605@gmail.com)
![Location](https://img.shields.io/badge/Ho%20Chi%20Minh%20City-Vietnam-DA251D?style=for-the-badge)
![Open to work](https://img.shields.io/badge/Open%20to-Fresher%2FJunior%20.NET%20roles-2EA043?style=for-the-badge)

</div>

## About me

- 💼 Former **Product Backend Intern at [GEEKUP](https://geekup.vn)** (09/2026 – 11/2026), working on a multi-tenant SaaS product.
- 🧱 There I built new APIs alongside a legacy service using the Strangler Fig pattern, writing characterization tests before changing any existing behaviour.
- 👥 I led the **backend team** on two capstone products, [AIDEFCOM](https://github.com/GFA25SE99-FA25SE211) and [FORMALE](https://github.com/EXE201-Formale).
- 🎓 B.Sc. Software Engineering, **FPT University** (2022 – 2026). Previously a Backend Developer Intern at **FPT Software**.
- 🤖 I use AI-assisted development (Claude Code, Codex), and every change still goes through code review and automated tests.

## Tech stack

| Area | Tools |
|---|---|
| **Languages** | <img src="https://skillicons.dev/icons?i=cs,ts,py" height="36" alt="C#, TypeScript, Python" /> &nbsp; ![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square) |
| **Backend** | <img src="https://skillicons.dev/icons?i=dotnet" height="36" alt=".NET" /> &nbsp; ![EF Core](https://img.shields.io/badge/EF%20Core-512BD4?style=flat-square) ![SignalR](https://img.shields.io/badge/SignalR-512BD4?style=flat-square) ![Swagger](https://img.shields.io/badge/OpenAPI-85EA2D?style=flat-square&logo=swagger&logoColor=black) |
| **Data** | <img src="https://skillicons.dev/icons?i=postgres,redis" height="36" alt="PostgreSQL, Redis" /> &nbsp; ![SQL Server](https://img.shields.io/badge/SQL%20Server%20%2F%20Azure%20SQL-CC2927?style=flat-square) |
| **Cloud & DevOps** | <img src="https://skillicons.dev/icons?i=azure,docker,git,gitlab,pnpm" height="36" alt="Azure, Docker, Git, GitLab, pnpm" /> &nbsp; ![Azure DevOps](https://img.shields.io/badge/Azure%20DevOps%20CI%2FCD-0078D7?style=flat-square) |
| **Testing & Quality** | <img src="https://skillicons.dev/icons?i=vitest,postman" height="36" alt="Vitest, Postman" /> &nbsp; ![xUnit](https://img.shields.io/badge/xUnit-5C2D91?style=flat-square) ![Testcontainers](https://img.shields.io/badge/Testcontainers-291A3F?style=flat-square) ![Zod](https://img.shields.io/badge/Zod-3E67B1?style=flat-square&logo=zod&logoColor=white) ![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square) |
| **Architecture** | Clean Architecture · Ports & Adapters · SOLID · Strangler Fig · Transactional Outbox · TDD |
| **AI** | OpenAI API · RAG / Vector Store · OpenRouter · Claude Code · Codex |

## Featured projects

### 🎟️ [Concert Ticket Booking Platform](https://github.com/minhcurus/concert-ticket-booking-platform)
`.NET 10` `EF Core` `PostgreSQL` `Redis` `xUnit` `Testcontainers` `Docker Compose`

A backend for booking concert tickets. The design goal was correctness under concurrent load: no overselling, no duplicate bookings, and no voucher over-redemption.
- Reservations use `SELECT … FOR UPDATE` row locks, taken in a fixed order to avoid deadlocks, with database constraints as the source of truth.
- `Idempotency-Key` on reserve, with a Redis `SETNX` fast path and a unique-constraint fallback.
- A `BackgroundService` expires unpaid holds and uses a Redis leader lock, so it stays safe when the service is scaled out.
- Integration tests run against real PostgreSQL and Redis through Testcontainers. Design notes are in [`docs/architecture.md`](https://github.com/minhcurus/concert-ticket-booking-platform/blob/master/docs/architecture.md).

### 🎓 [AIDEFCOM](https://github.com/GFA25SE99-FA25SE211): AI-powered thesis defense support system
`Backend Team Leader` `ASP.NET Core` `Azure SQL` `Redis` `SignalR` `Azure Blob Storage` `Docker` `Azure DevOps`

- I led the backend team and built REST APIs for defense sessions, scoring and reports, with real-time updates over SignalR.
- I designed the Azure SQL schema, the Redis caching and the Docker-based CI/CD pipeline on Azure DevOps.
- The system spans four repos: [API](https://github.com/GFA25SE99-FA25SE211/AIDefCom.API) (C#), [Web](https://github.com/GFA25SE99-FA25SE211/AIDefCom.Web) (Next.js), [Mobile](https://github.com/GFA25SE99-FA25SE211/AIDefCom.Mobile) and an [AI service](https://github.com/GFA25SE99-FA25SE211/AIDefCom.AIServer) for speech-to-text, voice authentication and duplicate-question detection.

### 👔 [FORMALE](https://github.com/EXE201-Formale/Formale_EXE201): AI-powered fashion e-commerce
`Backend Team Leader` `ASP.NET Core 8` `SQL Server` `EF Core` `Clean Architecture` `JWT` `Cloudinary` `PayOS` `OpenRouter`

- REST APIs for product search, filtering, pagination, image upload, reviews and PayOS payment.
- Built on Clean Architecture with DTOs and a service layer. An LLM suggests outfits that match each user's style.
- 🌐 [Landing page](https://formale-landing.vercel.app)

### 🤖 [chatbot-mini](https://github.com/minhcurus/chatbot-mini): RAG support assistant
`Python` `OpenAI Assistants API` `Vector Store` `Docker`

- Scrapes a Zendesk help center, converts the articles to Markdown and indexes them in an OpenAI Vector Store.
- A daily job re-uploads only new or changed articles. It keeps a manifest in GitHub so state survives on ephemeral hosts.

## Experience

**Product Backend Intern · [GEEKUP](https://geekup.vn)** · *09/2026 – 11/2026*<br/>
<sub>Multi-tenant SaaS product · NestJS, TypeScript, Vitest</sub>
- Built new APIs alongside a legacy service using the Strangler Fig pattern, writing characterization tests first.
- Delivered schema-validated REST APIs, including a bulk CSV import that returns a per-row issue report.
- Built authenticated, role-checked APIs with validated file uploads, plus a review flow for new applications.
- Made multi-step tenant provisioning retry-safe with per-step checkpoints, and moved email delivery to a **transactional outbox**.

**Backend Developer Intern · FPT Software** · *09/2024 – 12/2024*
- Developed and unit-tested C#/ASP.NET Core backend modules and service-layer logic alongside senior engineers.

## Awards & certifications

- 🏆 **Top Contributor Award**, Knowledge Sharing Contest, NIC × Google Digital Talent Community (2025)
- 📜 Google AI Essentials · Google Prompting Essentials (Coursera, 2025) · FPT Software OJT Program (2025)

<details>
<summary><b>📊 GitHub stats</b></summary>
<br/>
<div align="center">
<img src="https://github-readme-stats.vercel.app/api?username=minhcurus&show_icons=true&theme=transparent&hide_border=true&hide=contribs&custom_title=GitHub%20Stats&title_color=512BD4&icon_color=1F6FEB" height="165" alt="GitHub stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=minhcurus&layout=compact&langs_count=6&hide=html,css&theme=transparent&hide_border=true&title_color=512BD4" height="165" alt="Top languages" />
</div>
</details>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:512BD4,100:1F6FEB&height=90&section=footer" width="100%" alt="" />
