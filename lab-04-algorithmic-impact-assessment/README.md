# Algorithmic Impact Assessment of an AI Hiring Tool

**A formal GDPR and EU AI Act assessment of an "AI Talent Sourcing Assistant" that ranks candidates on "cultural fit"**

PhD 832: Ethics in Responsible AI · University of the Cumberlands · September 2026

[Full deliverables (PDF, 14 pages)](./Lab4_Algorithmic_Impact_Assessment_Ravula.pdf)

---

## The scenario

A recruiting system scans LinkedIn profiles and internal résumés, then ranks job candidates on "cultural fit" and "growth potential." Every part of that description raises a question. Were candidates told their data was being collected? Is "cultural fit" a proxy for age, caregiving, disability or social background? Is this a high-risk system under EU law?

## Method

I completed a formal **Algorithmic Impact Assessment in the EqualAI AIA Portal**, working through its structured risk questions across system description, context, data collection, classification, bias, and legal and compliance. I then produced three deliverables:

1. **AIA evidence and findings**: system description, data collection and bias findings, and a legal and compliance snapshot
2. **Data Integrity Justification Brief**: about 500 words on the tension between GDPR data minimization and the need for representative data
3. **Deployment Decision**: a Go / Conditional Go / No-Go recommendation defended against five factors, including likelihood and magnitude of harm, disparate effects, legal concerns and mitigability

## Key findings

**1. GDPR notice is failing right now, not as a future risk.** LinkedIn data is collected *about* candidates, not *from* them, so **GDPR Article 14** applies. Candidates must still be told who holds their data and why. They weren't, so the violation is near-certain and already happening.

**2. The scoring relies on proxies.** "Cultural fit" and "growth potential" draw on signals that correlate with protected characteristics. This creates a high likelihood of adverse impact on older candidates, caregivers, disabled applicants, and people outside dominant professional or educational networks.

**3. It is a high-risk system under the EU AI Act.** Systems that evaluate and filter job applicants are high-risk under **Article 6(2) and Annex III, point 4(a)**, and none of Article 6(3)'s narrow exceptions apply. That brings risk-management, human-oversight (Art. 14) and conformity-assessment (Art. 43) obligations that the system doesn't currently meet.

**4. Recommendation: No-Go for the current version.** An earlier draft recommended Conditional Go. I revised it because a live legal violation can't be offset by promises to fix it later, and the evidence couldn't justify overriding a high risk score. A future version could be reassessed after it has:
- A rewritten notice that names the data sources and outlines the scoring logic
- A documented lawful basis for the processing
- An independent adverse-impact audit, with high-risk proxy features removed
- Human review before any adverse decision
- The full EU AI Act high-risk compliance package

**The lesson:** when the evidence comes back as high risk, the conclusion has to follow it. A brief that argues Go anyway carries the burden of overriding its own instrument.

## Skills demonstrated

- Running a structured algorithmic impact assessment (EqualAI AIA Portal)
- GDPR analysis: Articles 13 vs. 14, lawful basis (Art. 6), special-category data (Art. 9) and automated decisions (Art. 22)
- EU AI Act classification and high-risk obligations
- Proxy-variable and adverse-impact analysis for hiring systems
- Writing a defensible deployment decision under regulatory risk

## Files

| File | Contents |
|---|---|
| [`Lab4_Algorithmic_Impact_Assessment_Ravula.pdf`](./Lab4_Algorithmic_Impact_Assessment_Ravula.pdf) | All three deliverables: AIA evidence and findings, Data Integrity Justification Brief, and the No-Go deployment decision |

## Key sources

- Regulation (EU) 2016/679 (General Data Protection Regulation), Articles 6, 9, 13, 14, 22 and 35.
- Regulation (EU) 2024/1689 (Artificial Intelligence Act), Articles 6, 14 and 43, and Annex III.
- Dewitte, P. (2025). AI meets the GDPR. In N. A. Smuha (Ed.), *The Cambridge handbook of the law, ethics and policy of artificial intelligence* (Ch. 7). Cambridge University Press.
- Solove, D. J., & Hartzog, W. (2025). The great scrape: The clash between scraping and privacy. *California Law Review*.
