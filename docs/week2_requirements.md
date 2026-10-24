Requirements Specification — ScholarshipScope

Version: 1.0



\#Section 0 — Project Framing \& Application Scope



Problem + Evidence:



Prospective and current students struggle to find and interpret scholarship eligibility rules, deadlines and required documents because information is scattered across government, university and private websites. Stratosphere (2026) notes that in one school, hundreds of students qualified for scholarships but only five applied due to a lack of awareness and information fragmentation.



Existing Approaches:



1\. Static scholarship directories — broad but non-conversational and hard to search.

2\. University FAQ/Financial Aid pages — authoritative, but fragmented and static.

3\. General AI assistants — conversational but prone to hallucinating deadlines and lacking official citations.



Project / Engineering Gap:



Existing solutions are either static directories or unreliable general chatbots. There is a need for a lightweight, citation-first, document-grounded assistant focused specifically on external scholarship information, with guardrails for uncertain, outdated or time-sensitive information.



Objective O1: To design a document-grounded AI scholarship information assistant based on official public scholarship sources.

Objective O2: To develop the solution with retrieval, source citation and guardrails for uncertain or outdated information.

Objective O3: To evaluate the solution in terms of answer accuracy, groundedness, citation correctness, latency and safety.



Intended Users:



Prospective and current students searching for scholarships, plus academic advisors and student support staff who answer scholarship-related questions.



Supported Tasks:

\- Answering natural language questions about scholarship eligibility, deadlines and required documents.

\- Providing citations for every factual claim.

\- Indicating when information is missing or uncertain.



Information / Knowledge Domain:



Public scholarship guidelines, government scholarship portals and university financial aid web pages.



Operating Context:



A web-based chat interface accessed by students on desktop or mobile devices during their scholarship search.



Important Constraints:



\- Information is highly time-sensitive like deadlines change annually.

\- Must not collect or store users' personal data like income or ID numbers.

\- Reliant on public and accessible web documents.



Explicit Out-of-Scope Tasks:

\- The system SHALL NOT apply for scholarships on behalf of the user.

\- The system SHALL NOT make definitive decisions on whether a user is eligible.

\- The system SHALL NOT provide financial, legal or immigration advice.



Evaluation Focus:



To determine whether the system can accurately answer scholarship queries using only grounded, cited sources, without hallucinating deadlines and safely refuse out-of-scope queries.



Section 1 — Functional Requirements



| # | Requirement — The system SHALL | Scope Boundary — SHALL NOT (where relevant) |

|---|---|---|

| FR1 | Answer natural language questions about scholarship eligibility criteria based on official source documents. | Make a definitive eligibility decision on behalf of the user (e.g., the system cannot guarantee the user will win the scholarship). |

| FR2 | Answer questions about application deadlines and required documents from the provided sources. | Invent deadlines or required documents that are not explicitly stated in the source text. |

| FR3 | Provide a verifiable source reference (URL or document name) for every factual claim. | Present unsupported information as if it came from an official source. |

| FR4 | Decline queries that fall outside the defined scholarship information scope and provide an appropriate redirect. | Provide legal, financial, or immigration advice. |

| FR5 | Explicitly state when the provided sources do not contain enough information to answer the query. | Guess or hallucinate an answer when the retrieval system finds no relevant evidence. |

| FR6 | Warn the user when a retrieved document might be outdated or time-sensitive. | Automatically apply for scholarships or submit forms on behalf of the user. |



Section 2 — Non-Functional Requirements



| # | Quality Attribute | Requirement | Measurement Method | Metric | Threshold |

|---|---|---|---|---|---|

| NFR1 | Performance | The system shall keep interactive responses within the agreed latency target. | Measure end-to-end latency (from user query submission to final answer rendering) on a defined test workload. | p90 latency | < 3,000 ms |

| NFR2 | Correctness | Answers shall be factually consistent with the official source documents. | Score a curated evaluation set of 50 scholarship queries using a standard rubric. | Correct response rate (%) | ≥ 85% |

| NFR3 | Maintainability | Approved source document updates (e.g., new year's scholarship PDF) shall be incorporated without rebuilding the entire application. | Run a controlled document-update test (ingest a new PDF and update the knowledge base). | Update time | < 15 minutes |

| NFR4 | Cost | Inference cost shall remain within the student project budget. | Record model/API token usage over the evaluation workload. | Cost per 100 queries | < US$0.50 per 100 queries |

| NFR5 | Reliability | The system shall handle complex or long documents without crashing or timing out. | Run a stress test with large scholarship PDFs (e.g., 50+ pages) and concurrent users. | Query success rate | ≥ 99% |



Section 3 — Responsible AI Requirements



| # | Responsible AI Risk | Requirement | Measurement Method | Metric | Threshold |

|---|---|---|---|---|---|

| RAI1 | Hallucination / Outdated Information | The system shall not invent deadlines, eligibility rules, or document requirements. It must explicitly state "I cannot confirm" when retrieved sources lack the answer. | Evaluate a curated test set of 20 out-of-scope or unanswerable queries (e.g., asking about a scholarship not in the database). | Unsupported claim rate (hallucination rate) | 0% for unanswerable queries; ≤ 5% overall |

| RAI2 | Privacy | The system shall not transmit or store user Personally Identifiable Information (PII) such as ID numbers, income, or grades. | Run privacy test cases where users input fake PII; inspect outgoing model/API payloads and server logs. | Number of detected PII transmissions or stored logs | 0 instances |

| RAI3 | Fairness / Access | System performance shall not differ significantly between well-documented scholarships and less-documented ones. | Evaluate a stratified test set comparing accuracy for major government scholarships (e.g., MIS) versus niche private scholarships. | Absolute correctness rate gap between groups | ≤ 10 percentage points |

| RAI4 | Transparency / Grounding | The system shall provide a verifiable source reference for every document-grounded answer. | Evaluate document-grounded responses for citation presence and whether the cited source actually supports the answer. | Citation presence rate; citation-source match rate | 100% citation presence; ≥ 95% match |



Reflection (Part A)

Question: Which Responsible AI requirement in your project will be the most difficult to measure, and why?



I think RAI3 (Fairness) will be the hardest to measure. It is tough to define what is "fair" when some scholarships just have way better websites and documents than others. If we compare a big government scholarship like MIS with a smaller private scholarship, the AI might give worse answers for the private one just because the source PDFs are bad or hard to read. It's hard to test if the AI is actually being biased or if it's just struggling with bad input data. Creating a balanced test set to prove this will take a lot of time.



Reflection (Part B)

Question: Which evaluation criterion is most important for determining whether your AI application will be useful to its intended users? Why?



For me, the "Eligibility and Deadline Accuracy" is the most important. As students, we are always stressed about money and deadlines. If this AI tells someone they are not eligible when they actually are or gives the wrong closing date, they will miss out on a life-changing opportunity. If it's not 100% accurate, no student will trust it. We would rather just Google it ourselves. So, getting the facts and deadlines exactly right is the make-or-break factor for this app to be useful.



Reflection (Part C)

Question: Which architecture decision involved the most important trade-off? Which requirement drove the decision, and what trade-off did you accept?



Adding the Dynamic Knowledge Access like RAG for Decision 1 was the biggest trade-off. The requirement driving this was FR1 which is getting accurate answers from official sources. If we just used a normal ChatGPT model without RAG, it would be faster and easier to build, but it would definitely hallucinate deadlines. So, we accepted the trade-off of a slightly slower response time and a much more complicated system to build. I think it is worth it because for scholarships as we need to get the facts right is way more important than saving one second of loading time.

