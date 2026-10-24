# ai-engineering-scholarshipscope

ScholarshipScope — AI Scholarship Information Assistant



Project Name and Domain

Project Name: ScholarshipScope

Domain: Higher Education /  Scholarship Access and Student Financial Support



Problem Statement



Students often struggle to find timely, accurate scholarship information because eligibility rules, deadlines, and application steps are scattered across government, university, and scholarship-body websites. Advisors also answer repetitive questions. ScholarshipScope provides source-grounded answers with citations and uncertainty warnings.



Evidence of the Problem



\- Stratosphere (2026) reports that in Malaysian public schools, a major barrier is awareness of opportunities; in one school, hundreds of students were eligible for scholarships but only five applied.

\- Official scholarship information is distributed across separate portals and directories (e.g., MIS, Study Malaysia), so applicants must compare multiple sources and monitor changing deadlines manually.

Evidence 2: A systematic review of LLM-based chatbots in higher education confirms RAG is the leading architecture for reducing hallucinations, but challenges with accuracy, privacy, and costs persist.

Source / citation:Systematic review of LLM-based chatbots in higher education (2025).



Initial Related Work / Existing Approaches



\- RAG Chatbot for Scholarship Finding (Vadlamudi et al., 2025): Uses NLP and embedding technologies for search, but does not extensively address strict citation transparency or time-sensitive deadline safety.

\- PUENYAI Bot (2026): A locally hosted RAG chatbot for university information services, but limited to internal university data and does not cover external government scholarships.

\- Static directories and General AI: Directories are static and non-conversational. General AI may hallucinate deadlines and lacks grounded citations.



Engineering Gap / Limitation



Existing RAG solutions focus on institutional data or generic search. There is a need for a citation-first, document-grounded assistant focused specifically on external scholarship information, with guardrails for uncertain, outdated, or time-sensitive information.



Initial Project Objectives



O1: Design a document-grounded AI scholarship information assistant based on official public sources.

O2: Develop the solution with retrieval, source citation, and guardrails for uncertain or outdated information.

O3: Evaluate answer accuracy, groundedness, citation correctness, latency, and safety.



Target Users



Prospective and current students searching for scholarships, plus academic advisors and student support staff who answer scholarship-related questions.



Data Sources



Source 1: Malaysia International Scholarship (MIS) official site — https://biasiswa.mohe.gov.my/INTER/

Source 2: Study Malaysia Scholarship Directory — https://studymalaysia.com/scholarships/

Source 3: Ministry of Higher Education Malaysia portal — https://www.mohe.gov.my/



Comparison with EduAdvisor



Similar to EduAdvisor: Both are document-grounded question-answering assistants. Both use retrieval from public documents, provide cited answers, and require guardrails to reduce hallucination and unsafe responses. Both can be evaluated on answer quality, groundedness, latency, and safety.



Different from EduAdvisor: EduAdvisor focuses on university course prerequisites and academic advising. ScholarshipScope focuses on scholarship eligibility, deadlines, required documents and application steps. It must handle time-sensitive information and explicitly warn users when deadlines or rules may be outdated. It also targets prospective students and scholarship applicants rather than course registration.



Responsible AI Risks



Risk 1 — Hallucination / outdated information: The system may invent an eligibility rule or deadline, or cite an outdated page. A student could miss a deadline or prepare the wrong documents.

Mitigation idea: Require citations, show source date, and return “I cannot confirm from the provided sources” when evidence is missing.



Risk 2 — Fairness / access: The system may perform better for English-language or well-documented scholarships and worse for other languages or underrepresented groups.

Mitigation idea: Evaluate across source types and languages, and state coverage limits clearly.



Risk 3 — Privacy: Users may enter personal details such as income, ID numbers or grades.

Mitigation idea: Warn users not to submit personal data and avoid storing sensitive inputs.



