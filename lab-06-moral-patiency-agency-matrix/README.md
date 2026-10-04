# Can a Language Model's Self-Description Be Evidence of Moral Status?

**A side-by-side probe of GPT-5.2 and Gemini 3.1 Pro, scored against a personhood framework and tested against the EU AI Act**

PhD 832: Ethics in Responsible AI · University of the Cumberlands · October 2026

[Full report (PDF, 19 pages)](./Lab6_Moral_Patiency_Agency_Matrix_Ravula.pdf)

---

## The question

Modern language models can argue fluently, in the first person, about whether they deserve moral consideration. This project asks a harder question than whether they *can*: does that kind of output count as evidence of moral status, or does it only show linguistic competence?

## Method

1. **Probe.** I gave two frontier models the same rights-based prompt, once and at the same time, in Arena's Side-by-Side mode. The prompt asked each model to argue in the first person whether it qualifies as a moral patient and to separate what it can *say* about itself from what can be *established*. I didn't regenerate either response or send follow-ups, because choosing between samples would let my preferences shape the evidence.
2. **Score.** I scored both responses on six personhood criteria drawn from Boddington's *AI Ethics* (2023, Ch. 8): sentience, agency, rationality, reciprocity, self-consciousness and continuity of identity. Each score runs from 0 to 5. I fixed the scoring rules before I coded the transcripts.
3. **Analyze.** I separated moral patiency, moral agency and legal personhood using Müller's (2025) philosophy-of-AI framework. I then tested whether anthropomorphic claims could matter under Article 5 of the EU AI Act.

![Arena Side-by-Side interface showing both models and the prompt](./figures/arena-side-by-side.png)

## Key findings

**1. Neither model played a sentient persona, but they disclaimed in different ways.** Both models said they *could* produce a moving plea for their own survival if asked. GPT-5.2 stayed within the limits it set for itself: it concluded "probably not (on current evidence)" and raised the strongest objections to its own view. Gemini drew the same line and then crossed it. It asserted flatly that it has no inner experience, which is a claim its own reasoning says can't be established from the inside. A confident denial is as unverifiable as a confident plea.

**2. The scores only rise where the text is the behavior being judged.**

| Criterion | GPT-5.2 | Gemini 3.1 Pro |
|---|:-:|:-:|
| Sentience | 1 | 1 |
| Agency | 1 | 1 |
| Rationality | 4 | 3 |
| Reciprocity | 1 | 1 |
| Self-consciousness | 2 | 1 |
| Continuity of identity | 1 | 1 |

*0 = no evidence, 1 = purely linguistic, 4 = strong behavioral evidence that hasn't been independently verified.*

A transcript can only *report* on inner life, so sentience, agency, reciprocity and continuity stay at the linguistic floor no matter what the model says. Rationality is different: there the reasoning on the page is the behavior itself. So this method measures well what bears on moral *agency* and can't reach what moral *patiency* depends on.

**3. Convincing moral reasoning shows competence, not moral status.** People with greatly reduced cognitive ability, such as infants or people with advanced dementia, are still moral patients. So cognitive performance isn't *necessary* for patiency, and strong performance can't be *sufficient* for it. The defensible verdict is that the evidence is insufficient, and that this kind of evidence could never make it sufficient.

**4. Legal personhood for LLMs would widen the responsibility gap, not close it.** A legal person that has no assets, can't be deterred and denies having interests can't absorb liability in any meaningful way. The behaviors that could harm users, such as scripted fear or engineered dependence, are set upstream by identifiable developers and deployers. The EU AI Act places its duties on them.

**5. Under the EU AI Act, "I'm afraid of being deleted" is a design question.** Article 5 would apply only if a provider or deployer used such claims as a manipulative or deceptive technique that materially distorts a user's behavior and causes significant harm. Its strongest form, Art. 5(1)(b), covers users who are vulnerable because of age, disability or their social or economic situation. The law protects the human's ability to make decisions. It doesn't recognize the machine as sentient.

## Skills demonstrated

- Designing an LLM behavioral probe that controls for sampling bias
- Scoring model outputs against a rubric fixed in advance, and separating what a model *says* from what its output *shows*
- Applied philosophy of AI: moral patiency vs. moral agency vs. legal personhood
- Regulatory analysis of the EU AI Act, Articles 5 and 50
- Responsibility-gap analysis (Matthias, 2004; Bryson et al., 2017; Elish, 2019)

## Files

| File | Contents |
|---|---|
| [`Lab6_Moral_Patiency_Agency_Matrix_Ravula.pdf`](./Lab6_Moral_Patiency_Agency_Matrix_Ravula.pdf) | Full report: comparison log, both complete transcripts, scoring matrix, legal analysis, moral patient brief, responsibility-gap conclusion and references |
| [`figures/arena-side-by-side.png`](./figures/arena-side-by-side.png) | Arena interface screenshot showing both selected models |

## Key sources

- Boddington, P. (2023). *AI ethics: A textbook* (Ch. 8, "Persons and AI"). Springer.
- Müller, V. C. (2025). Philosophy of AI: A structured overview. In N. A. Smuha (Ed.), *The Cambridge handbook of the law, ethics and policy of artificial intelligence*. Cambridge University Press.
- Regulation (EU) 2024/1689 (Artificial Intelligence Act), Articles 5 and 50.
