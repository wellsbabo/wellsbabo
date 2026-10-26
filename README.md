<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1944f0,100:f4f0f0&height=180&section=header&text=Backend%20%E2%86%92%20Applied%20AI%20Engineer&fontColor=ffffff&fontSize=40&fontAlignY=38" />

  <h3>I connect AI to the business systems people already use — and make it safe to run in production.</h3>

  <a href="https://jungkwan.pages.dev/"><img src="https://img.shields.io/badge/Portfolio-1944f0?style=flat-square&logo=googlechrome&logoColor=white" /></a>
  <a href="https://jungkwan.pages.dev/blog/"><img src="https://img.shields.io/badge/Tech%20Blog-282d33?style=flat-square&logo=rss&logoColor=white" /></a>
  <a href="https://jungkwan.pages.dev/projects/"><img src="https://img.shields.io/badge/Projects-282d33?style=flat-square&logo=github&logoColor=white" /></a>
</div>

<br />

## 👋 About

Backend engineer with **5+ years** of experience building insurance and game business systems — external integrations, authentication, and high-volume batch processing.
I'm now moving toward **applied AI engineering** — and I work like a **forward-deployed engineer**: I sit with the people doing the work, find where their time actually goes, and ship AI into their existing systems *within* the API, auth, and data constraints already in place.

- 🏢 **Now** — Software Engineer at an insurance company, building the sales-support platform and its integrations
- 🎮 **Before** — Backend Engineer at a game company (game services, in-app purchases, internal tools)
- 🛡️ **Started in** — Cybersecurity at a government agency, which shaped how I think about trust, auth, and secrets

## 🧭 How I Work

| | Principle | In practice |
|:-:|---|---|
| ↔️ | **Connect systems** | Understand the boundaries of APIs, auth, and data, and keep business flows intact across them. |
| 🔁 | **Make failure manageable** | Design for partial failure, retries, and duplicates — and always leave a state you can recover from. |
| ✳️ | **Put AI to real work** | Automate the repetitive parts of people's jobs, then verify results against existing data before trusting them. |

## 🚀 Selected Work

**⚡ Monthly batch → Transactional Outbox** &nbsp;`8h → 1h 20m`
<br />A monthly batch over tens of thousands of contracts called an external API synchronously per record, so any downstream delay stalled the whole job. I split DB updates and outbound requests into an outbox written in the same transaction, added an async sender with a state machine (pending → processing → done / failed → retry), per-record `REQUIRES_NEW` isolation, unique constraints for dedup, and idempotency checks. The core batch now finishes in ~10 minutes; failed items are traceable and replays skip already-processed records.
<br />`Java` `Spring Boot` `MariaDB` `RabbitMQ` · [Write-up ↗](https://jungkwan.pages.dev/posts/large-batch-external-sync-outbox-pattern/)

**🤖 AI-assisted reporting automation** &nbsp;`1–2 days → under 5 min`
<br />A monthly executive report required joining thousands of rows from 5 tables by hand in Excel. I mapped the report's sources and rules, built a Python generator with AI coding tools, and validated it against months of past manual reports. It's still in production use on request.
<br />`Python` `SQL` `AI coding tools`

**🔐 Auth & data integration across 4 systems**
<br />Integrated the sales platform with a next-gen core system, the insurer's legacy core, webmail, and a third-party quote service — each with its own auth model (token issuance, token exchange via API Gateway, Microsoft Entra ID SSO). Centralized integration tokens in Redis so new features share one issuance path.
<br />`Spring Boot` `Redis` `Entra ID` `OAuth / SSO`

**🧩 Fixing the request, not the limit** &nbsp;`~9,000 multipart parts → 1`
<br />Bulk registration of 3,000 users hit Tomcat's `FileCountLimitExceededException`. Instead of raising a server-protection limit, I restructured the payload into a single JSON field with a dedicated DTO and added per-reason failure logging.
<br />`Spring Boot` `Jackson` `Vue.js` · [Write-up ↗](https://jungkwan.pages.dev/posts/tomcat-multipart-part-limit-json-refactoring/)

**🛠️ CI & secrets** — Replaced Git submodules with Jenkins-side multi-repo composition to eliminate recurring pointer conflicts, and moved backend secrets to AWS Secrets Manager. [Write-up ↗](https://jungkwan.pages.dev/posts/git-submodule-merge-conflict-jenkins-build/)

**🧾 Server-side in-app purchase verification** — Verified Google Play purchases on the server via the Android Publisher API (service account), with order-ID dedup, so only verified purchases grant entitlements — never trusting the client.

## 🧪 Side Projects

| Project | What it is | Highlights | Stack |
|---|---|---|---|
| [**AI LoL Coach Bot**](https://jungkwan.pages.dev/projects/opgg-discord-bot/) | Discord bot that answers game questions and coaches matchups via OP.GG MCP + LLM tool calls | Switched MCP transport from SSE to JSON-RPC over HTTP POST; parallelized independent tool calls (matched by call ID) to cut 8–10s sequential responses; rewrote in Go as a single binary (~500MB → ~30MB RAM) | `OpenAI API` `MCP` `Go` `Java` |
| [**Telegram Automation Bot**](https://jungkwan.pages.dev/projects/telegram-automation/) | Scheduled news summaries with sources, A/B content drafts, and monthly API cost tracking | Flags summaries when source text is insufficient | `OpenAI API` `Go` `Telegram` |
| [**AI Video Pipeline**](https://jungkwan.pages.dev/projects/remotion-automation/) | Script → scenes → media → TTS → rendered video | Human review in the loop; published videos with ~1.7K views | `Remotion` `Voicebox` `GenAI` |
| [**NyamNyam**](https://jungkwan.pages.dev/projects/nyamnyam/) | Recipe manager iOS app, built and shipped solo | **#1 Paid in Food & Drink** (KR App Store), #25 overall paid; RLS per-user access, receipt-verified premium | `Flutter` `Supabase` `RevenueCat` |
| [**ReddiBridge**](https://jungkwan.pages.dev/projects/reddibridge/) | AI lead finder for Reddit, shipped on the Mac App Store with subscriptions | Sunset — taught me to validate platform data-access and distribution risk *before* building | `Flutter` `Supabase` `GenAI` |

## 🛠️ Tech Stack

**Backend** &nbsp;
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" />
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />

**Data** &nbsp;
<img src="https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white" />
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white" />

**AI** &nbsp;
<img src="https://img.shields.io/badge/OpenAI%20API-412991?style=flat-square&logo=openai&logoColor=white" />
<img src="https://img.shields.io/badge/MCP-000000?style=flat-square&logo=anthropic&logoColor=white" />
<img src="https://img.shields.io/badge/LLM%20Tool%20Calling-282d33?style=flat-square" />

**Auth & Security** &nbsp;
<img src="https://img.shields.io/badge/OAuth%202.0-EB5424?style=flat-square&logo=auth0&logoColor=white" />
<img src="https://img.shields.io/badge/Microsoft%20Entra%20ID-0078D4?style=flat-square&logo=microsoft&logoColor=white" />
<img src="https://img.shields.io/badge/AWS%20Secrets%20Manager-DD344C?style=flat-square&logo=amazonwebservices&logoColor=white" />

**Infra & Tools** &nbsp;
<img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" />
<img src="https://img.shields.io/badge/GitLab-FC6D26?style=flat-square&logo=gitlab&logoColor=white" />
<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" />

**Client** &nbsp;
<img src="https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white" />

## ✍️ Latest Writing

<sub>Posts are written in Korean. Updated daily from the [blog RSS](https://jungkwan.pages.dev/rss.xml).</sub>

<!-- BLOG:START -->
- [대용량 배치와 외부 연동을 안전하게 만들기: Outbox 패턴 적용기](https://jungkwan.pages.dev/posts/large-batch-external-sync-outbox-pattern/) — 2026-10-01
- [Git submodule 충돌을 없애기 위한 Jenkins 빌드 구조 변경](https://jungkwan.pages.dev/posts/git-submodule-merge-conflict-jenkins-build/) — 2026-09-11
- [Tomcat multipart part 제한을 설정 상향 대신 요청 구조 개선으로 해결](https://jungkwan.pages.dev/posts/tomcat-multipart-part-limit-json-refactoring/) — 2026-09-09
<!-- BLOG:END -->

## 🎯 What I Want to Build Next

> Forward-deployed, AI-powered tools that operators run themselves —
> designed to stay safe inside existing APIs, permissions, and failure boundaries.

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:f4f0f0,100:1944f0&height=100&section=footer" />
</div>
