V1 Architecture Decisions \& Traceability — ScholarshipScope



1\. Architecture Needs (Step C2)

Based on the requirements and evaluation criteria, the simple `User → Model → Response` architecture is insufficient. We need the following additions:



| Requirement ID | What does the requirement need? | Architecture Response |

|---|---|---|

| FR3 / RAI4 | Answers must include verifiable source references. | Access to scholarship information sources and a Source Tracking component. |

| RAI1 | Out-of-scope queries must be appropriately refused. | Scope / Safety Control component. |

| NFR2 | Scholarship answers must meet the defined correctness threshold. | Access to relevant scholarship knowledge sources (RAG). |

| NFR1 | Responses must meet the defined latency threshold. | A sufficiently efficient interaction path between the application and AI capability. |



2\. Architecture Decision Records (ADR)



Decision 1: Include Dynamic Knowledge Access (RAG)

\- Requirement / Constraint: Answers must be grounded in approved, up-to-date scholarship information (FR1, NFR2).

\- Alternatives Considered: Base model only; static search.

\- Selected Option: Dynamic knowledge access (Retrieval-Augmented Generation).

\- Trade-off Accepted: More system complexity and a slightly higher latency (NFR1), but significantly better grounding and traceability.



Decision 2: Include Explicit Scope \& Safety Control

\- Requirement / Constraint: Out-of-scope queries must be refused, and hallucinations prevented (RAI1, FR4).

\- Alternatives Considered: Instruction-only via system prompt.

\- Selected Option: Explicit scope-control component (guardrail).

\- Trade-off Accepted: Possible false refusals and additional processing time, but much higher safety and reliability.



3\. Initial Requirements Traceability Matrix



| Objective | Requirement | Evaluation Criterion | Architecture Element | Later Evidence |

|---|---|---|---|---|

| O1 | FR1, FR2 | Eligibility and Deadline Accuracy | Knowledge Source / Retrieval System | Test results from 50-query evaluation set |

| O2 | FR3, RAI4 | Source Citation and Support | Source Tracking / Application Interface | Citation match rate from evaluation set |

| O2 | RAI1, FR5 | Hallucination and Uncertainty Handling | Scope / Safety Control | Refusal rate on out-of-scope test queries |

| O3 | NFR1 | Response Latency | Application Interface / AI Capability | p90 latency logs |

