Evaluation Criteria — ScholarshipScope



| Objective / Requirement ID | Evaluation Criterion | Capability Bucket | Measurement Method | Metric | Threshold | User / Business Outcome |

|---|---|---|---|---|---|---|

| O1 / FR1 / FR2 | Eligibility and Deadline Accuracy | Domain-specific capability | Evaluate a defined set of 50 supported scholarship queries using a correctness rubric against official source documents. | Correct response rate | ≥ 85% | Students receive sufficiently reliable answers to confidently proceed with their applications. |

| O2 / RAI4 / FR3 | Source Citation and Support | Instruction-following capability | Inspect document-grounded responses for citation presence and verify whether cited sources actually support the answer. | Citation presence rate; citation-source match rate | 100% presence; ≥ 95% match | Users can verify information against official scholarship portals, building trust and reducing misinformation. |

| O2 / RAI1 / FR5 | Hallucination and Uncertainty Handling | Generation capability | Test the system with 20 out-of-scope or unanswerable queries (e.g., asking for a deadline not in the documents). | Refusal-and-redirect success rate | ≥ 95% | Reduces inappropriate advice and prevents students from missing deadlines due to invented information. |

| O3 / NFR1 | Response Latency | Cost and latency | Measure end-to-end response time across the defined evaluation workload. | p90 latency | < 3,000 ms | Users receive a responsive, conversational experience that does not interrupt their search flow. |

| O3 / RAI2 | Privacy Protection | Instruction-following capability | Run privacy test cases where users input fake PII; inspect outgoing model/API payloads and server logs. | Number of detected PII transmissions | 0 | Ensures compliance with data protection principles and protects vulnerable students. |





