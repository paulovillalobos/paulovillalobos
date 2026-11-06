# Paulo Villalobos

Founder of **[FOAAP Lda](https://tecnologia.foaap.app/)**, a software company in Porto, Portugal.
Backend systems, data pipelines, machine learning. Contracts: [paulo@foaap.app](mailto:paulo@foaap.app)

### saneamento-engine — a Portuguese sovereign LLM that reads building applications and cannot invent a word

**[github.com/paulovillalobos/saneamento-engine](https://github.com/paulovillalobos/saneamento-engine)** · live demo **[lei.foaap.app](https://lei.foaap.app)**

The Portaria that lists what a building application must contain, decomposed into 642 hashed passages and 88 rules,
and a Portuguese 9B model fine-tuned on it through twelve rounds under a grammar that only lets it answer with what is
literally on the page. Code decides, the técnico signs. 66 planted errors found out of 66 on test sets frozen before
training, zero false alarms; "cannot decide" is a scored success. EUPL-1.2, commercial licence on request.
`Python` `vLLM` `LoRA` `Modal` `law as data`

**3rd place, "Mapping CORDIS projects to SDGs"**, European Data Portal, Publications Office of the
European Union, Luxembourg, 4 November 2026, for [Nexus CORDIS](https://nexus.foaap.app/#/).

### Merged upstream

- **European Commission, EUDI Wallet reference issuer**: [eudi-srv-web-issuing-eudiw-py#195](https://github.com/eu-digital-identity-wallet/eudi-srv-web-issuing-eudiw-py/pull/195)
- **Direção-Geral do Território, recartDGT QGIS plugin**: [recart-plugin#104](https://github.com/dgterritorio/recart-plugin/pull/104) (invalid-geometry check), [#105](https://github.com/dgterritorio/recart-plugin/pull/105) (per-version mapping files)
- **Autenticação.gov (Cartão de Cidadão middleware), Qt 6 port**: [csoares/autenticacao.gov#1](https://github.com/csoares/autenticacao.gov/pull/1), Linux and Flatpak build on Qt 6, now part of [amagovpt/autenticacao.gov#258](https://github.com/amagovpt/autenticacao.gov/pull/258)
- **Carris Metropolitana website**: [carrismetropolitana/website#342](https://github.com/carrismetropolitana/website/pull/342)
- **mc-router**: [itzg/mc-router#637](https://github.com/itzg/mc-router/pull/637)

Every number below comes from code in the linked repository.

---

### Backend

**[macro-vintages](https://github.com/paulovillalobos/macro-vintages)**
Euro-area macro data from the ECB and Eurostat in PostgreSQL, keeping every
value the system has ever held, so the API can answer what a series said at any
past moment. Workers claim jobs with `SKIP LOCKED` and lease fencing; race tests
run six processes against each other, and a mutation check removes each lock in
turn to prove a test catches it. Async FastAPI with ETags, hashed API keys and
rate limits. 120 tests, 0 inconsistent reads in 9,406 under load.
`Python` `FastAPI` `PostgreSQL` `asyncpg`

**[audio-jobs](https://github.com/paulovillalobos/audio-jobs)**
Background-job system in Go on Postgres and Redis Streams: at-least-once
delivery, retries, a dead-letter queue, lease fencing. In the chaos test 1,000
of 1,000 jobs finish while workers are killed mid-job and Redis loses its data.
Profiling took throughput from 162 to 532 jobs/s.
`Go` `PostgreSQL` `Redis` `Docker`

### Data

**[pt-open-data-pipeline](https://github.com/paulovillalobos/pt-open-data-pipeline)**
Portuguese card-spending statistics (INE) for 308 municipalities since 2020:
immutable raw layer, DuckDB, dbt marts, incremental loads, Parquet. Its 82 data
tests caught a published inconsistency: a region-month where INE reports 0 online
transactions while its 13 municipalities add up to 2,553.
`Python` `SQL` `dbt` `DuckDB`

### Infrastructure

**[platform-infra](https://github.com/paulovillalobos/platform-infra)**
Runs audio-jobs on Kubernetes with Prometheus alerts on SLOs and six scripted
failure drills (worker kills, a Postgres crash, a Redis wipe, a bad deploy rolled
back automatically), 0 jobs lost. The Terraform for private GKE, Cloud SQL and
Workload Identity was applied to a real GCP project, checked (11/11, each with a
negative test), drilled under load and destroyed; the real run found six bugs
that static checks had passed.
`Kubernetes` `Terraform` `Prometheus` `Bash`

### Machine learning and AI

**[cordis-field-classifier](https://github.com/paulovillalobos/cordis-field-classifier)**
Classifies 52,000 EU research projects into 37 fields. A fine-tuned transformer
reaches 0.709 micro-F1 and holds it on a later funding programme it never saw,
where TF-IDF drops to 0.637. Bootstrap intervals on every number. The official
export makes pandas silently drop 285 rows; the reader here recovers them.
`PyTorch` `Transformers` `scikit-learn` `FastAPI`

**[incident-agent](https://github.com/paulovillalobos/incident-agent)**
Ten injected faults in a small OpenTelemetry-instrumented system, an agent that
investigates them through read-only tools, and a harness that scores every
report against ground truth with code: citations must exist, fixes must survive
a re-run of the incident. A local 4B model finds the right service in 60% of
runs but never the full cause; my rule-based baseline gets 70%.
`Python` `OpenTelemetry` `React` `TypeScript`

### Libraries

**[mesh-governance](https://github.com/paulovillalobos/mesh-governance)**
Evidence store with append-only history enforced by database triggers,
idempotent commands and review bound to exact revisions. 42 tests, standard
library only, `mypy --strict`.

### Security

While reading a public procedures catalogue, I found an SMTP credential being
sent to the browser by a software platform that Portuguese municipalities use.
I reported it to the vendor and the municipality, with CERT.PT in copy, and the
vendor confirmed the same day that it was fixed for every affected client.

---

Also: [foaap-engine-public](https://github.com/paulovillalobos/foaap-engine-public) ·
[energy-baseline-public](https://github.com/paulovillalobos/energy-baseline-public) ·
[bicis-sapiens-web](https://github.com/paulovillalobos/bicis-sapiens-web) ·
live: [NEXUS](https://nexus.foaap.app/#/), [FOAAP](https://tecnologia.foaap.app/)
