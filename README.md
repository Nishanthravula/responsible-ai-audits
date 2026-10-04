# Responsible AI Audits

Hands-on audits and analyses of AI systems, completed during my PhD in Artificial Intelligence at the University of the Cumberlands for the course Ethics in Responsible AI (PhD 832). Each project evaluates a real or realistic AI system for fairness, accountability, legal compliance, social impact or moral status. Each one pairs an empirical probe or audit with the relevant ethics literature and the EU AI Act.

**Nishanth Ravula** · Software engineer (ML and full-stack) · Austin, TX

---

## Projects

| # | Project | What I did | Tools and frameworks |
|---|---|---|---|
| 1 | [**Does an AI Research Assistant Faithfully Summarize Its Source?**](./lab-01-ai-summary-integrity-audit/) | Audited a NotebookLM summary claim by claim against the primary text. Found six discrepancies (page conflations, an overstated "consensus," a dropped caveat, a footnote treated as a main claim, and a misattributed chapter), none of them an outright fabrication. | Google NotebookLM, traceability matrix, discrepancy taxonomy |
| 2 | [**Forensic Bias Audit of a Recidivism Risk Model**](./lab-02-forensic-bias-audit/) | Audited a COMPAS-like model for individual reliability and racial error-rate disparity. Applying Equal Opportunity cut disparity by 85% for a 0.63-point accuracy cost. Defended a Conditional Go to a mock board. | What-If Tool, Kleinberg impossibility theorem, NIST AI RMF |
| 3 | [**Feature Attribution and the Responsibility Gap**](./lab-03-feature-attribution-responsibility-gap/) | Used single-feature experiments on a census-income model to show that capital gain and marital status (both proxies) drove a misprediction. Argued that explainability is a prerequisite for accountability. | What-If Tool, counterfactuals, UCI Adult dataset |
| 4 | [**Algorithmic Impact Assessment of an AI Hiring Tool**](./lab-04-algorithmic-impact-assessment/) | Ran a formal AIA on a candidate-ranking system. Found a live GDPR Art. 14 notice violation, proxy-driven scoring and an EU AI Act high-risk classification, leading to a No-Go for the current version. | EqualAI AIA Portal, GDPR, EU AI Act Annex III |
| 5 | [**AI, Labor Transformation and Displacement**](./lab-05-labor-automation-displacement/) | Compared AI-exposure tools across three occupations, audited the Duolingo contractor reduction, and drafted a worker-centric AI policy with enforceable triggers. | TripleTen, AI Labor Index, OECD AI Incidents Monitor, ILO R166/R198 |
| 6 | [**Can a Language Model's Self-Description Be Evidence of Moral Status?**](./lab-06-moral-patiency-agency-matrix/) | Gave GPT-5.2 and Gemini 3.1 Pro the same rights-based prompt side by side and scored both on six personhood criteria. Found that convincing moral reasoning shows competence, not moral status, and that legal personhood for LLMs would widen the responsibility gap. | Arena, Boddington's personhood criteria, EU AI Act Art. 5 and 50 |


## Approach

Across these projects I try to keep three things separate:

- **What a system says vs. what its behavior shows.** A model's self-report, or a dashboard's headline metric, is a claim to test, not a finding.
- **Moral, legal and technical questions.** For example, whether a model is fair, whether it's lawful and whether it's explainable are related but different questions.
- **Where responsibility lands.** I trace outcomes back to the design and deployment decisions made by identifiable people and organizations.

## About

These are course projects. Assignment prompts are paraphrased rather than reproduced. Model outputs are included as recorded evidence, with each model and its access date identified.
