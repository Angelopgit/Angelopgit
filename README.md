<h1 align="center">Angelo Perez</h1>

<p align="center">
  <b>Systems-minded engineer moving into AI application design</b><br>
  Senior IT Analyst at L'Oréal USA &nbsp;|&nbsp; Full-stack SaaS builder &nbsp;|&nbsp; Open-source contributor
</p>

<p align="center">
  New York / New Jersey &nbsp;&middot;&nbsp;
  <a href="mailto:angelopereznet@gmail.com">angelopereznet@gmail.com</a> &nbsp;&middot;&nbsp;
  English, Spanish
</p>

<br>

## About

I build software where reliability matters: billing, licensing, auth, installers and the failure modes between them. I'm now applying that discipline to AI applications, and I read upstream AI code closely enough to find silent failures: swallowed errors, no-op assignments and unhandled edge cases.

**Focus areas**

- **AI application design:** how models, tools, data and users fit together into software people can rely on (inference pipelines, agent tooling, local and offline LLM apps, time-series models).
- **Reliability over demos:** reproducing bugs, writing minimal fixes and explaining the root cause.
- **Shipping real products:** payments, licensing, access control, deployment and documentation.

<br>

## Featured Project: PERSCOM Advance

A commercial, self-hosted personnel-management platform for military-simulation units, sold by subscription (monthly or annual) with automated license delivery.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Discord.js](https://img.shields.io/badge/Discord.js-5865F2?style=flat-square&logo=discord&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)

| | |
|:--|:--|
| **Scope** | 3 repositories (product, license server, marketing site), 12-table schema, 60+ REST endpoints, role-based access (admin, moderator, member), Discord bot integration, one-command installer |
| **Challenge** | Self-hosted software runs where you can't control it. Subscriptions had to be enforced without a customer's unit going offline when my license server is briefly unreachable. |
| **Solution** | A license server with key validation on startup and every 24 hours, a **72-hour offline grace period**, per-IP rate limiting and an audit log. Stripe webhooks drive the full lifecycle: checkout, key generation, emailed delivery, renewal, cancellation and failed-payment warnings, plus a nightly expiry job. |
| **Also hard** | Modeling a self-referential unit hierarchy (units, sub-units, personnel), promotion and transfer workflows, and keeping the Discord bot and web app consistent on one database. |
| **Result** | A working product from payment to running install, with documented deployment (PM2, nginx, TLS) and a public [marketing site](https://github.com/Angelopgit/perscom-advance-site). |

[perscom-advance](https://github.com/Angelopgit/perscom-advance) &nbsp;|&nbsp; [perscom-advance-site](https://github.com/Angelopgit/perscom-advance-site) &nbsp;|&nbsp; License server (private)

<br>

## Open-Source Contributions to AI Projects

I look for real bugs in AI tooling, reproduce them and send minimal, well-explained fixes.

| Project | Contribution | Status |
|:--|:--|:--:|
| **[google-research/timesfm](https://github.com/google-research/timesfm)**<br>Google Research's pretrained time-series foundation model | [PR #401](https://github.com/google-research/timesfm/pull/401): fixed three silent inference bugs. An all-NaN input returned a plausible zero-padded context instead of an empty array (wrong forecasts, no error). A NumPy truth-value check was slated to raise in future releases. A `torch.compile(self)` call only rebound a local variable, so the default-on compile **never applied**. | ![Open](https://img.shields.io/badge/Open-DBAB09?style=flat-square) |
| **[morluto/rea](https://github.com/morluto/rea)**<br>Agent-driven reverse-engineering toolkit | [PR #2241](https://github.com/morluto/rea/pull/2241): the CIL decoder omitted the `no.` prefix opcode (ECMA-335 §2.2), so valid .NET methods were reported as malformed. Traced it to the opcode table, fixed it and added a regression test. | ![Merged](https://img.shields.io/badge/Merged-8250DF?style=flat-square) |
| **[AtomicBot-ai/Atomic-Chat](https://github.com/AtomicBot-ai/Atomic-Chat)**<br>Open-source ChatGPT alternative that runs 100% offline | [PR #2](https://github.com/AtomicBot-ai/Atomic-Chat/pull/2): replaced duplicated search-index construction across the thread store's mutation actions with one shared helper (+21 / -55 lines, no behavior change). | ![Merged](https://img.shields.io/badge/Merged-8250DF?style=flat-square) |
| **[nidhaloff/deep-translator](https://github.com/nidhaloff/deep-translator)**<br>Multi-engine translation library | [PR #305](https://github.com/nidhaloff/deep-translator/pull/305): an exception was constructed but never raised, so an empty API response crashed later with a confusing `AttributeError`. | ![Open](https://img.shields.io/badge/Open-DBAB09?style=flat-square) |

<br>

## AI Projects

**[TokenBiasDetect](https://github.com/Angelopgit/Tokenbiasdetect)**
A Flask web app that compares two texts and charts the probability of bias in each, using a pretrained transformer classifier (`d4data/bias-detection-model`) through Hugging Face Transformers. My first Python and ML project. I started on PyTorch and moved to TensorFlow to resolve dependency conflicts, which showed me early how much of ML engineering is environment and packaging.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)

**Next: AI layer for PERSCOM** *(planned, not yet shipped)*
Natural-language roster queries and draft after-action reports over the existing API, designed with explicit guardrails, permission-aware retrieval and evaluations.

<br>

## Technical Skills

| | |
|:--|:--|
| **Languages** | JavaScript, TypeScript, Python, SQL, Bash |
| **Application** | Node.js, Express, React, Vite, REST API design, authentication and RBAC, Stripe and webhook integration |
| **AI / ML** | Hugging Face Transformers, TensorFlow, PyTorch (exposure), inference pipelines |
| **Infrastructure** | Docker, Git, PM2, nginx, Azure, AWS, GCP, Microsoft Entra ID |
| **Security and compliance** | PCI DSS, Cybersecurity GRC, DSPM |
| **Delivery** | Agile and Scrum, technical requirements, integration specifications |

<br>

## Experience

**Senior IT Analyst, MarTech: L'Oréal USA** &nbsp;|&nbsp; promoted January 2026
Scrum Master for a consumer-activation platform. Writes technical requirements and integration specs, and builds the dashboards that track delivery. Previously led retail IT buildouts, 24+ device mPOS rollouts, PCI-compliant payment-terminal upgrades and an enterprise DSPM integration (Salesforce and Databricks).

**Education:** B.S. Computer Information Systems (Cybersecurity minor), Kean University

<br>

## Contact

Open to AI application engineering, applied AI and LLM tooling, and full-stack roles.

**Email:** [angelopereznet@gmail.com](mailto:angelopereznet@gmail.com)
