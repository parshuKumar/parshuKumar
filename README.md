# Parshuram Kumar

**Backend engineer — distributed systems, concurrency correctness, and telephony/CTI integration.**
Node.js · TypeScript · MySQL · Redis · AWS

I build systems that stay correct when things go wrong: duplicate webhooks, lost locks, dead Redis, racing workers. Most of my work is in production call-center and legal-consultation infrastructure — high write concurrency, unreliable third-party event delivery, and hard auditability requirements.

[Portfolio](https://parshuramkumar.vercel.app) · [LeetCode](https://leetcode.com/u/Parshuram01/) · [Email](mailto:parshuramkumarsde@gmail.com)

---

## What I'm actually good at

**Concurrency under real load.** Killed a production double-assignment race in a poll-driven inbound call router using three layered defenses — an atomic conditional `UPDATE` agent claim, a guarded assignment write, and a Redis `SET NX` per-call single-flight lock with cached-response replay. Verified with a harness firing 10 simultaneous claimers against real MySQL, not mocks.

**Making unreliable providers behave.** Built a unified status-resolution engine mapping 20+ telephony statuses across three incompatible webhook schema versions into a single direction-, duration-, and DB-aware enum. Analyzing real call data against it surfaced 13 production bugs — duplicate-webhook races, cross-version field mismatches, business logic silently overwriting telephony state.

**Query design over query count.** Collapsed dashboard aggregation from 15+ queries to 2 by reusing the same bucket SQL for counts and lists, so a count can never disagree with the list it summarizes. 4× on the statistics endpoint, ~50% latency cut on the highest-traffic search API.

**Degrade, don't fail.** Redis loss drops single-flight while the DB claim preserves correctness. Webhooks return 200 on internal error so providers stop retrying. S3 migration, transcription, and auto-disposition run post-response, off the hot path.

**Schemas that remember.** Self-referential reschedule chains instead of destructive updates, append-only JSON change trails carrying actor and reason, versioned AI transcriptions under a unique `(call, version)` index, read-shaped composite indexes over UTC storage with explicit IST business-day SQL.

---

## Open source & side projects

### [prod-alert-sentry](https://github.com/parshuKumar/prod-alert-sentry) — [npm](https://www.npmjs.com/package/prod-alert-sentry)
Error-monitoring package for Node services. Event-driven, ~500 alerts/day in production, with retry logic, severity routing, context enrichment, and structured log rotation. Cut debugging turnaround ~70% on the team that runs it.
`Node.js` `TypeScript` `Slack API`

### [chatwithpdf](https://github.com/parshuKumar/chatwithpdf) — [live](https://chatwithpdf-sigma.vercel.app/)
RAG document QA with source citation. 800-token chunking, Gemini embeddings, cosine similarity in pgvector on Postgres, token-streaming responses, provider-agnostic model layer, input validation and rate limiting.
`Next.js` `TypeScript` `Prisma` `pgvector` `Gemini`

---

## Stack

<p align="left">
  <img src="https://skillicons.dev/icons?i=ts,nodejs,express,nestjs,fastapi,python,mysql,postgres,mongodb,redis&theme=dark" alt="Backend stack" />
  <br />
  <img src="https://skillicons.dev/icons?i=react,nextjs,docker,kubernetes,aws,githubactions,jenkins,git,postman,cpp&theme=dark" alt="Frontend and infra" />
</p>

| | |
|---|---|
| **Languages** | TypeScript, JavaScript (Node.js), Python, SQL, C/C++ |
| **Backend** | Express, NestJS, Fastify, FastAPI · REST, microservices, API gateway, JWT/RBAC, Socket.IO |
| **Systems** | Distributed locking, concurrency control, idempotency, background jobs, feature flags |
| **Data** | MySQL, PostgreSQL, MongoDB, Redis · Sequelize, TypeORM, Prisma · index & query design |
| **AI** | LLM integration (Gemini, Claude, OpenAI), RAG, pgvector, prompt versioning, token/cost accounting |
| **Frontend** | React, Next.js (App Router), Zustand, SWR, WebRTC softphone integration |
| **Infra** | Docker, Kubernetes, AWS S3, GitHub Actions, Jenkins, New Relic |

---

## Elsewhere

450+ problems on LeetCode, 136+ on GeeksforGeeks. Currently going deeper on systems design and Kubernetes-side operability.

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=parshuKumar&layout=compact&theme=transparent&hide_border=true&langs_count=6" height="150" alt="Top languages" />
</p>
