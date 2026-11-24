# Paulo Villalobos

Founder of **[FOAAP](https://foaap.app)**. We build trust infrastructure for Europe: systems that make identity,
credentials and decisions verifiable. Porto, Portugal · [paulo@foaap.app](mailto:paulo@foaap.app)

### cunho: credentials in the European Digital Identity Wallet

**[github.com/paulovillalobos/cunho](https://github.com/paulovillalobos/cunho)** · try it on your phone: **[demo.foaap.app](https://demo.foaap.app)**

An open-source issuer for the EU Digital Identity Wallet: OpenID4VCI 1.0, SD-JWT VC, HAIP, and revocation in seconds
through a Token Status List. It works with independent wallets (Lissi, Paradym) and issues straight from Moodle.
Institutions keep their own name and their own key; FOAAP runs it and keeps it current with every change to the
specifications. AGPL-3.0, with an Apache-2.0 edition.
`OpenID4VCI` `SD-JWT VC` `eIDAS 2.0` `Moodle`

### ccp-engine — does every Portuguese public contract follow the law?

**[github.com/paulovillalobos/ccp-engine](https://github.com/paulovillalobos/ccp-engine)** · live **[contratos.foaap.app](https://contratos.foaap.app)**

A deterministic engine that reads the Código dos Contratos Públicos as data (40,088 passages, every wording with the
dates it was in force) and checks all 1,487,586 procedures on the BASE portal against it with 101 typed rules. Each
verdict cites the article, the literal text in force on that date and the facts it used: 32,578 comply, 240 do not,
the rest say why they cannot be decided. Models propose readings of the law, code decides, and no model runs at
verdict time; a hash-chained governance log makes every result replayable. EUPL-1.2.
`Python` `PostgreSQL` `Cloud Run` `React` `law as data`

**3rd place, "Mapping CORDIS projects to SDGs"**, European Data Portal, Publications Office of the
European Union, Luxembourg, 4 November 2026, for [Nexus CORDIS](https://nexus.foaap.app/#/).

### Merged upstream

- **European Commission, EUDI Wallet reference issuer**: [eudi-srv-web-issuing-eudiw-py#195](https://github.com/eu-digital-identity-wallet/eudi-srv-web-issuing-eudiw-py/pull/195)
- **Direção-Geral do Território, recartDGT QGIS plugin**: [recart-plugin#104](https://github.com/dgterritorio/recart-plugin/pull/104) (invalid-geometry check), [#105](https://github.com/dgterritorio/recart-plugin/pull/105) (per-version mapping files)
- **Autenticação.gov (Cartão de Cidadão middleware), Qt 6 port**: [csoares/autenticacao.gov#1](https://github.com/csoares/autenticacao.gov/pull/1), Linux and Flatpak build on Qt 6, now part of [amagovpt/autenticacao.gov#258](https://github.com/amagovpt/autenticacao.gov/pull/258)
- **Carris Metropolitana website**: [carrismetropolitana/website#342](https://github.com/carrismetropolitana/website/pull/342)
- **mc-router**: [itzg/mc-router#637](https://github.com/itzg/mc-router/pull/637)

### More engineering

- **[saneamento-engine](https://github.com/paulovillalobos/saneamento-engine)**: the Portaria on building applications as 642 hashed passages and 88 rules; 66 of 66 planted errors found, zero false alarms.
- **[macro-vintages](https://github.com/paulovillalobos/macro-vintages)**: euro-area macro data in PostgreSQL with full revision history; 120 tests, 0 inconsistent reads in 9,406 under load.
- **[audio-jobs](https://github.com/paulovillalobos/audio-jobs)**: background jobs in Go on Postgres and Redis Streams; 1,000 of 1,000 jobs survive killed workers and a Redis wipe.
- **[platform-infra](https://github.com/paulovillalobos/platform-infra)**: Kubernetes, SLO alerts and six failure drills with 0 jobs lost; Terraform applied to real GCP and destroyed.
- **[pt-open-data-pipeline](https://github.com/paulovillalobos/pt-open-data-pipeline)**: INE card-spending data with 82 dbt tests that caught a published inconsistency.
- **[cordis-field-classifier](https://github.com/paulovillalobos/cordis-field-classifier)**: 52,000 EU research projects into 37 fields, robust on a funding programme it never saw.
- **[mesh-governance](https://github.com/paulovillalobos/mesh-governance)**: evidence store with append-only history enforced by the database; `mypy --strict`.

### Security

While reading a public procedures catalogue, I found an SMTP credential being
sent to the browser by a software platform that Portuguese municipalities use.
I reported it to the vendor and the municipality, with CERT.PT in copy, and the
vendor confirmed the same day that it was fixed for every affected client.

---

Live: [foaap.app](https://foaap.app) · [demo.foaap.app](https://demo.foaap.app) · [contratos.foaap.app](https://contratos.foaap.app) · [NEXUS](https://nexus.foaap.app/#/)
