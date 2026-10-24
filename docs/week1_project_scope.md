Project Name and Domain

Project Name: ScholarshipScope

Domain: Higher Education / Scholarship Access and Student Financial Support



Problem Statement



Prospective and current students often struggle to find and interpret scholarship eligibility rules, deadlines, required documents and application steps because information is scattered across government, university and scholarship-body websites. Students may miss opportunities or waste time comparing inconsistent pages, while academic advisors answer repetitive questions. An AI-based solution is appropriate because a document-grounded assistant can retrieve information from official public sources, answer natural-language questions, cite the source and explicitly flag when information is missing or uncertain.



Evidence of the Problem



Evidence 1: Scholarship awareness and access are a documented problem. Stratosphere (2026) reports that in Malaysian public schools, a major barrier is not student ability but awareness of opportunities; in one Sabah school, hundreds of students qualified for scholarships but only five applied.  

Source / citation: Stratosphere (2026). Are Scholarships Out of Reach? — https://stratsea.com/2026/09/24/are-scholarships-out-of-reach/



Evidence 2: Official scholarship information is distributed across separate government, university, and private directories, so applicants must compare eligibility, deadlines, and application instructions across multiple sources.  

Source / citation: Malaysia International Scholarship (MIS) — https://biasiswa.mohe.gov.my/INTER/  

Source / citation: Study Malaysia Scholarship Directory — https://studymalaysia.com/scholarships/



Initial Related Work / Existing Approaches



Study / solution 1: Retrieval-Augmented Generation (RAG) Chatbot for Scholarship Finding (Vadlamudi et al., 2025)  

Source / citation: IEEE Xplore (2025).  

Key limitation: Focuses on generic natural language search and embedding technologies but does not extensively address strict citation transparency or time-sensitive deadline safety in a localized context.



Study / solution 2: PUENYAI Bot: A locally hosted RAG chatbot for university information services (2026)  

Source / citation: IEEE Xplore (2026).  

Key limitation: Answers enquiries on curricula and scholarships using institutional sources. However, it is limited to internal university data and may not cover external government or private scholarship bodies.



Study / solution 3: Static scholarship directories (e.g., Study Malaysia) and general-purpose AI (ChatGPT/Claude)  

Source / citation: https://studymalaysia.com/ and general LLMs.  

Key limitation: Directories are static and non-conversational. General AI is conversational but may hallucinate deadlines or eligibility rules and lacks grounded citations from official documents.



Engineering Gap / Limitation



Existing RAG solutions focus on institutional data or generic search. There is a need for a lightweight, citation-first, document-grounded assistant focused specifically on external scholarship information, with guardrails for uncertain, outdated or time-sensitive information.



Initial Project Objectives



O1: To design a document-grounded AI scholarship information assistant based on official public scholarship sources.  

O2: To develop the solution with retrieval, source citation, and guardrails for uncertain or outdated information.  

O3: To evaluate the solution in terms of answer accuracy, groundedness, citation correctness, latency, and safety.



Target Users



\- Prospective undergraduate and postgraduate students searching for scholarships.

\- Current university students checking eligibility and deadlines.

\- Academic advisors or student support staff who answer scholarship-related questions.



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

