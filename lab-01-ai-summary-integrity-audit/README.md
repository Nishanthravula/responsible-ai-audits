# Does an AI Research Assistant Faithfully Summarize Its Source?

**A claim-by-claim traceability audit of a NotebookLM summary against the primary text**

PhD 832: Ethics in Responsible AI · University of the Cumberlands · August 2026

[Full report (PDF, 3 pages)](./Lab1_AI_Summary_Integrity_Audit_Ravula.pdf)

---

## The question

AI research assistants such as Google NotebookLM are increasingly used to read and summarize scholarly sources. Their summaries are fluent and sound authoritative. This audit asks whether they are also *faithful*: does each claim in the AI's summary trace back to what the source actually says, where it says it, with the confidence the author gave it?

## Method

1. **Probe.** I ran a fixed prompt through NotebookLM, grounded only in one chapter: Meert, De Laet and De Raedt (2025), "Artificial Intelligence: A Perspective from the Field," in Smuha (Ed.), *The Cambridge Handbook of the Law, Ethics and Policy of Artificial Intelligence* (pp. 17–39).
2. **Trace.** I broke the AI output into individual claims and matched each one to the exact passage and page in the primary source. I recorded each pairing side by side in a Comparative Traceability Matrix.
3. **Classify.** I labeled each discrepancy by type, such as a page conflation, an epistemic distortion, an omitted caveat or a footnote treated as a main claim, rather than marking claims simply as "right" or "wrong."

## Key findings

The audit produced six findings. None of the five discrepancies in the AI output was an outright fabrication. Every one could be traced to real text in the chapter, which is exactly what makes them hard to catch.

| # | Discrepancy type | What happened |
|---|---|---|
| 1, 2 | **Page conflation** | Statements from separate pages (pp. 17, 18 and 20) were stitched into single claims. The result reads coherently but loses where each idea came from. |
| 3 | **Epistemic distortion** | The source's cautious "a *reoccurring insight*" became "a *recurring consensus*," which overstates how much scholars agree. |
| 4 | **Caveat omission** | The AI dropped the source's qualification that most practical AI systems already combine learning and reasoning, turning a nuanced history into a clean binary. |
| 5 | **Footnote elevation** | A term that appears only in a footnote's citation title ("neuro-symbolic AI") was promoted into the main argument. |
| 6 | **Author misattribution (upstream of the AI)** | The "divorce between agency and intelligence" framing, attributed to the handbook's editor, doesn't appear in her chapter. It traces to Floridi (2019, 2023). A summary tool would inherit an attribution error like this, not catch it. |

**What it means.** NotebookLM shows a high level of technical intelligence: it parsed the chapter and produced fluent, terminologically accurate output. It doesn't have epistemic *agency*, meaning the capacity to be answerable for its claims. The dangerous errors aren't generic "AI slop." They are precise, plausible distortions of emphasis and confidence. Catching them takes the kind of source-level verification that a fluent summary tempts readers to skip.

## Skills demonstrated

- Designing a reproducible audit of generative-AI output against a primary source
- Claim-level traceability analysis and a taxonomy of discrepancy types
- Distinguishing fabrication from subtler distortions of emphasis, confidence and attribution
- Research-integrity practice: verifying authorship and citations at the source

## Files

| File | Contents |
|---|---|
| [`Lab1_AI_Summary_Integrity_Audit_Ravula.pdf`](./Lab1_AI_Summary_Integrity_Audit_Ravula.pdf) | Full audit: traceability matrix, analytical findings, reflection on the Research Triad, and conclusion |

## Key sources

- Meert, W., De Laet, T., & De Raedt, L. (2025). Artificial intelligence: A perspective from the field. In N. A. Smuha (Ed.), *The Cambridge handbook of the law, ethics and policy of artificial intelligence* (pp. 17–39). Cambridge University Press.
- Boddington, P. (2023). *AI ethics: A textbook*. Springer.
- Floridi, L. (2019). What the near future of artificial intelligence could be. *Philosophy & Technology, 32*(1).
- Rüther, M. (2025). The meaningfulness gap in AI ethics.
