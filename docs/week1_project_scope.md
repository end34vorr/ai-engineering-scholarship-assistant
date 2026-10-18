Project Name and Domain

Project Name: UniFAQ — AI University FAQ Assistant  

Domain: Higher Education / Student Administrative Support



Problem Statement

University information is scattered across faculties, departments and administrative units. Students nowadays more prefer conversational search but must navigate hierarchical websites to find answers about policies, deadlines and procedures. An AI assistant can provide instant, citation-grounded answers, reducing repetitive queries for staff.



Evidence of the Problem

Evidence 1:Cho \& Kim (2025) state that the decentralized information structure of university websites hinders Gen Z's information retrieval efficiency; over 43.5% of Gen Z prefer conversational search over keyword or hierarchy-based navigation.

Source / citation: Cho, H., \& Kim, J. (2025). RAG-based university information chatbot with hybrid retrieval and system-prompt control.



Evidence 2: A systematic review of LLM-based chatbots in higher education confirms RAG is the leading architecture for reducing hallucinations, but challenges with accuracy, privacy, and costs persist.  

Source / citation:Systematic review of LLM-based chatbots in higher education (2025).



Initial Related Work / Existing Approaches



Study / solution 1: Marcel — RAG-based conversational agent for prospective student admission inquiries  

Source / citation: Mühling, A. (2025). Marcel: A RAG-based conversational agent for university admission inquiries.  

Key limitation: Focused on admissions, not ongoing student FAQs across policies and procedures.



Study / solution 2: RAG-based university information chatbot with hybrid retrieval  

Source / citation: Cho, H., \& Kim, J. (2025). RAG-based university information chatbot with hybrid retrieval and system-prompt control.  

Key limitation: Evaluated on a Korean university context; does not address citation transparency or multilingual policy documents.



Study / solution 3: Course advising RAG chatbot evaluation  

Source / citation: Evaluation study of a RAG-based course advising chatbot (2026).  

Key limitation: Reports a 5.7% hallucination rate even with RAG, showing grounding is not solved; focused on course advising, not general administrative FAQs.



Engineering Gap / Limitation

Existing RAG chatbots focus on admissions or course advising. There is a gap for a lightweight, citation-first assistant that grounds answers across a specific university’s scattered policy, procedure, and deadline documents, with explicit uncertainty handling when a query spans multiple sources.



Initial Project Objectives

O1:To design a document-grounded FAQ assistant for university policies and procedures.  

O2: To develop retrieval with source citation and uncertainty flagging.  

O3: To evaluate accuracy, groundedness, citation correctness, and latency.



Target Users

\- New Undergraduate and postgraduate students.

\- Front-line administrative staff who answer repetitive queries.



&#x20;Data Sources

Source 1: University Student Handbook PDF — \[replace with your university’s public handbook URL]  

Source 2: Academic Regulations / Examination Rules page — \[replace with your university’s public regulations URL]  

Source 3: Faculty FAQ or Student Services page — \[replace with your university’s public FAQ URL]



Comparison with EduAdvisor

Similar to EduAdvisor: Both are document-grounded Q\&A assistants with citation and guardrail requirements. Both use retrieval from public documents and can be evaluated on answer quality, groundedness, latency and safety.



Different from EduAdvisor: EduAdvisor focuses on course prerequisites and graduation requirements. UniFAQ covers the broader administrative FAQ space (fees, deadlines, policies and procedures).



Responsible AI Risks

Risk 1 — Hallucination: The system may invent a policy deadline or procedure.  

Mitigation idea: Require citations and return “I cannot confirm from the provided sources” when evidence is missing.



Risk 2 — Outdated information: Policies change annually; the system may cite an older handbook without warning.  

Mitigation idea: Display source dates and flag when a document may be outdated.



Risk 3 — Privacy: Students may enter personal ID or fee information.  

Mitigation idea: Warn users not to submit personal data and avoid storing sensitive inputs.

