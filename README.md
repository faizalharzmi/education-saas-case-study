# Education SaaS Case Study

Clean-room architecture case study for an education and assessment platform.

## Publication boundary

This repository is an independent design exercise using synthetic roles, entities, workflows, and data. It is **not** a publication of CerdasLab, UKPC, PKSK, Atom Telecom, or any employer system. No private source code, customer data, credentials, internal deployment details, or confidential terminology is included.

If a future implementation is added, it must be independently owned or explicitly licensed for publication and must pass a separate redaction/privacy review.

## Product problem

An assessment platform needs to support students, guardians, educators, and administrators without mixing account management, entitlement, assessment delivery, scoring, and reporting into one opaque workflow. It must preserve answer provenance and explain how a result was produced.

## Case studies

| Document | Focus |
| --- | --- |
| [Architecture](docs/architecture.md) | Product boundaries, authentication, deployment, and request flow |
| [Assessment engine](docs/assessment-engine.md) | Attempts, question selection, timing, scoring, and auditability |
| [Reporting](docs/reporting.md) | Read models, exports, access controls, and data retention |
| [AI-assisted marking](docs/ai-assisted-marking.md) | Human-in-the-loop design, confidence, privacy, and fallback |
| [Data model](docs/data-model.md) | Entity relationships and integrity constraints |

## Engineering position

The design favours explicit roles, immutable assessment evidence, deterministic scoring where possible, asynchronous report generation, and clear boundaries around any AI-assisted suggestion. It does not claim live users, accuracy percentages, or production scale.

## Validation

This repository is documentation-only. Its CI workflow verifies the required case studies and Mermaid diagrams remain present.

## License

MIT. See [LICENSE](LICENSE).
