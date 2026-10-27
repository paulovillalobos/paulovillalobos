# Paulo Villalobos

Software engineer. Backend systems, data pipelines, machine learning.
Porto, Portugal · remote · [CV](https://github.com/paulovillalobos/paulovillalobos/blob/main/Paulo-Villalobos-CV.pdf) · [paulo@foaap.app](mailto:paulo@foaap.app)

Most of my work has been private: I keep notes, designs and experiments locally
in CherryTree, and started publishing on GitHub in 2026. The projects below are
recent builds on problems I'd been working on privately, from EU research data
and Portuguese public statistics to job systems and infrastructure. Every number
below comes from code in the linked repository.

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
live: [NEXUS](https://nexus.foaap.app/#/), [FOAAP](https://foaap.app/)
