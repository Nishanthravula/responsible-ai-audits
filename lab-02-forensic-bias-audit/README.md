# Forensic Bias Audit of a Recidivism Risk Model

**Individual reliability, group fairness and the impossibility trade-off in a COMPAS-like pretrial system, with a board-level deployment defense**

PhD 832: Ethics in Responsible AI · University of the Cumberlands · September 2026

[Evidence Pack](./Lab2_Part1_Forensic_Evidence_Pack_Ravula.pdf) · [Impossibility Brief](./Lab2_Part1_Impossibility_Brief_Ravula.pdf) · [Board deck](./Lab2_Part2_Stakeholder_Defense_Deck_Ravula.pdf)

---

## The question

Pretrial risk tools score defendants on how likely they are to reoffend, and those scores can affect someone's liberty. This audit asks three questions about a COMPAS-like classifier. Does it behave consistently for individuals? Does it distribute errors fairly across racial groups? And can it be deployed responsibly, given that some fairness goals are mathematically incompatible?

## Method

**Part 1: Forensic audit (Google What-If Tool)**
1. **Monotonicity probes.** I chose three borderline defendants whose risk scores fell within 0.008 of the 0.5 threshold. I increased `priors_count` by one for each and checked that the risk score never moved the wrong way.
2. **Counterfactual analysis.** I found the nearest oppositely classified record (L1 distance) to identify which features drive classification flips.
3. **Group fairness.** I sliced performance by race, compared false positive rates, false negative rates and base rates, then applied an Equal Opportunity constraint and measured the accuracy cost.

**Part 2: Stakeholder defense**
I turned the findings into a 15-slide Board of Directors presentation with narration (12–18 minutes). It makes a Go / Conditional Go / No-Go recommendation backed by NIST AI RMF governance controls.

## Key findings

**1. The model is monotonic, but borderline outcomes are fragile.** Adding one prior offense raised the risk score in all three trials (+0.098 to +0.110). For one defendant, that single change flipped the label from Low Risk to High Risk. The nearest counterfactual differed only in `priors_count`, not in race or other demographics.

**2. Errors fall on different groups in opposite directions.**

| Group (n) | Base rate | FPR | FNR |
|---|:-:|:-:|:-:|
| African-American (1,904) | 53.5% | 24.5% | 11.4% |
| Caucasian (1,111) | 42.8% | 9.6% | 23.7% |

African-American defendants who would not reoffend were wrongly flagged High Risk far more often. Caucasian defendants who would reoffend were wrongly cleared more often. This matches the pattern ProPublica found in the original COMPAS analysis.

**3. Fairness was cheap: the "ethical tax" was 0.63 points.** Equal Opportunity thresholds (0.59 / 0.39) cut combined error disparity from 27.2 to 4.1 points, an **85% reduction**. Weighted accuracy fell only from 65.1% to 64.4%.

**4. Kleinberg's impossibility theorem applies directly.** Because base rates differ by 10.7 points and the model is far from perfect (AUC 0.71), it can't be calibrated and satisfy Equal Opportunity at the same time. Choosing which error matters more is a governance decision, not a technical setting.

**5. Recommendation: Conditional Go.** Deploy only at the Equal Opportunity thresholds, with these conditions:
- Mandatory human review of every score within 0.05 of the threshold
- Quarterly sliced-metric disclosure
- Automatic suspension if disparity triggers fire (for example, combined disparity above 10 points)
- An explicit ban on race-based manual overrides

## Skills demonstrated

- Model auditing in Google's What-If Tool: monotonicity, counterfactuals and sliced metrics
- Fairness metrics: FPR/FNR parity, Equal Opportunity and the accuracy cost of fairness
- Applying Kleinberg et al.'s (2016) impossibility theorem to real audit data
- AI governance design: NIST AI RMF controls, human oversight and monitoring triggers
- Explaining technical findings to an executive board

## Files

| File | Contents |
|---|---|
| [`Lab2_Part1_Forensic_Evidence_Pack_Ravula.pdf`](./Lab2_Part1_Forensic_Evidence_Pack_Ravula.pdf) | Monotonicity trials, counterfactuals, fairness tables and ethical-tax calculation |
| [`Lab2_Part1_Impossibility_Brief_Ravula.pdf`](./Lab2_Part1_Impossibility_Brief_Ravula.pdf) | About 1,500 words on Kleinberg's theorem, defending the ethical weighting (λ), and NIST AI RMF alignment |
| [`Lab2_Part2_Stakeholder_Defense_Deck_Ravula.pdf`](./Lab2_Part2_Stakeholder_Defense_Deck_Ravula.pdf) | 15-slide board presentation recommending Conditional Go |

## Key sources

- Kleinberg, J., Mullainathan, S., & Raghavan, M. (2016). Inherent trade-offs in the fair determination of risk scores. *arXiv:1609.05807*.
- National Institute of Standards and Technology. (2023). *AI Risk Management Framework (AI RMF 1.0)*.
- Wexler, J., et al. (2020). The What-If Tool: Interactive probing of machine learning models. *IEEE Transactions on Visualization and Computer Graphics, 26*(1).
