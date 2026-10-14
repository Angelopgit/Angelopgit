# Hi, I'm Angelo Perez 👋

**Systems-minded engineer moving into AI application design.**
Senior IT Analyst at L'Oréal USA by day, shipping a commercial full-stack SaaS and contributing fixes to open-source AI projects on my own time.

📍 New York / New Jersey · 📫 [angelopereznet@gmail.com](mailto:angelopereznet@gmail.com) · 🗣️ English, Spanish

---

## What I'm focused on

- **AI application design**: how models, tools, data and users fit together into software people can rely on (inference pipelines, agent tooling, offline/local LLM apps, time-series models).
- **Reliability over demos**: I read upstream code closely enough to find the silent failures: swallowed errors, no-op assignments, bad edge-case handling.
- **Shipping real products**: billing, licensing, auth, installers and docs, not just the happy path.

---

## 🚀 Featured project: PERSCOM Advance

A commercial, self-hosted personnel-management platform for military-simulation units, sold by subscription (monthly or annual) with automated license delivery.

**Stack:** Node.js · Express · React · Vite · SQLite · Discord.js · Stripe · Nodemailer · PM2 / nginx

| | |
|---|---|
| **Scope** | 3 repos (product, license server, marketing site), 12-table schema, 60+ REST endpoints, role-based access (admin / moderator / member), Discord bot integration, one-command installer |
| **Why it was hard** | Selling *self-hosted* software means you can't control where it runs. I had to enforce subscriptions without a customer's unit going dark when my server blips. |
| **What I built** | A license server with key validation on startup and every 24 h, a **72-hour offline grace period**, per-IP rate limiting, and an audit log. Stripe webhooks drive the full lifecycle: checkout → key generation → emailed delivery → renewal → cancellation → failed-payment warnings, plus a nightly expiry job. |
| **Also hard** | Modeling a self-referential unit hierarchy (units → sub-units → personnel), promotion and transfer workflows, and keeping the Discord bot and web app consistent on one database. |
| **Result** | A working product end to end, from payment to a running install, with documented deployment (PM2, nginx, TLS) and a [marketing site](https://github.com/Angelopgit/perscom-advance-site). |

Repos: [perscom-advance](https://github.com/Angelopgit/perscom-advance) · [perscom-advance-site](https://github.com/Angelopgit/perscom-advance-site) · license server (private)

---

## 🤖 Open-source contributions to AI projects

I look for real bugs in AI tooling, reproduce them, and send minimal, well-explained fixes.

| Project | What it is | My contribution | Status |
|---|---|---|---|
| [**google-research/timesfm**](https://github.com/google-research/timesfm) | Google Research's pretrained time-series foundation model | [PR #401](https://github.com/google-research/timesfm/pull/401): fixed three silent inference bugs. An all-NaN input returned a plausible zero-padded context instead of an empty array (wrong forecasts, no error); a NumPy truth-value check slated to raise in future releases; and a `torch.compile(self)` call that only rebound a local variable, so the default-on compile **never applied**. | 🟡 Open |
| [**morluto/rea**](https://github.com/morluto/rea) | Agent-driven reverse-engineering toolkit, from app behavior down to native binaries | [PR #2241](https://github.com/morluto/rea/pull/2241): the CIL decoder omitted the `no.` prefix opcode (ECMA-335 §2.2), so valid .NET methods were reported as *malformed*. Traced it to the opcode table, fixed it, and added a regression test. | ✅ Merged |
| [**AtomicBot-ai/Atomic-Chat**](https://github.com/AtomicBot-ai/Atomic-Chat) | Open-source ChatGPT alternative that runs 100% offline | [PR #2](https://github.com/AtomicBot-ai/Atomic-Chat/pull/2): replaced duplicated search-index construction across the thread store's mutation actions with one shared helper (21 additions, 55 deletions, no behavior change). | ✅ Merged |
| [**nidhaloff/deep-translator**](https://github.com/nidhaloff/deep-translator) | Multi-engine translation library | [PR #305](https://github.com/nidhaloff/deep-translator/pull/305): an exception was constructed but never raised, so an empty API response crashed later with a confusing `AttributeError`. | 🟡 Open |

---

## 🧪 AI projects

**[TokenBiasDetect](https://github.com/Angelopgit/Tokenbiasdetect)** is a Flask web app that compares two texts and charts the probability of bias in each, using a pretrained transformer classifier (`d4data/bias-detection-model`) through Hugging Face Transformers. My first Python/ML project. I started on PyTorch and moved to TensorFlow to resolve dependency conflicts, which taught me early how much of ML engineering is environment and packaging.

**Next up:** adding an AI layer to PERSCOM (natural-language roster queries and draft after-action reports over the existing API), designed with explicit guardrails, permission-aware retrieval and evals. 🔜 *Planned, not yet shipped.*

---

## 🛠️ Toolbox

![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-FFD21E?logo=huggingface&logoColor=black)
![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?logo=stripe&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white)
![GCP](https://img.shields.io/badge/GCP-4285F4?logo=googlecloud&logoColor=white)

**Strengths:** REST API design · auth & RBAC · payment/webhook integration · CI-friendly installers · cloud & identity (Entra ID) · endpoint management · security & compliance (PCI DSS, GRC, DSPM) · Agile delivery

---

## 💼 Day job

**Senior IT Analyst, MarTech: L'Oréal USA** (promoted Jan 2026). Scrum Master for a consumer-activation platform; I write technical requirements and integration specs, and build the dashboards that track delivery. Previously led retail IT buildouts, 24+ device mPOS rollouts, PCI-compliant payment-terminal upgrades and an enterprise DSPM integration (Salesforce + Databricks).

🎓 B.S. Computer Information Systems (Cybersecurity minor), Kean University

---

## 📬 Let's talk

Open to AI application engineering, applied AI / LLM tooling, and full-stack roles. The fastest way to reach me is email: **angelopereznet@gmail.com**
