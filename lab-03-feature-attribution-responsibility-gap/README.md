# Feature Attribution and the Responsibility Gap

**Using local interpretability on a census-income model to ask who is responsible when a biased feature drives a decision**

PhD 832: Ethics in Responsible AI · University of the Cumberlands · September 2026

[Full report (PDF, 7 pages)](./Lab3_Feature_Attribution_Responsibility_Gap_Ravula.pdf)

---

## The question

When a model's prediction rests on a feature that carries historical bias, such as marital status standing in for gender, who is responsible for the economic harm: the developer, the data provider, or "the system"? I also defend a second claim: **explainability is a prerequisite for accountability.**

## Method

I audited two income classifiers trained on the UCI Census Income (Adult) dataset in Google's What-If Tool:

1. **Feature exploration.** I examined feature distributions to find candidate proxy variables.
2. **Find an anomaly.** I located datapoint 259: a 72-year-old with a professional-school degree (education-num = 15) whom *both* models predicted to earn ≤$50K.
3. **Isolated single-feature experiments.** The public demo doesn't expose SHAP bars, and the instructor approved counterfactual and manual editing instead. I changed one feature at a time (sex, occupation, hours per week, marital status, capital gain) and recorded how each model's score moved.
4. **Keep statistics and causes apart.** Each result describes the *model's decision boundary*, not what actually caused the person's income.

## Key findings

**1. Wealth and household status drove the prediction more than education.** Changing capital gain from $0 to $7,000 had the largest single-feature effect, flipping both models (scores of 0.983 and 0.798). Changing marital status from never married to married had the largest effect of any demographic or labor feature (0.603 and 0.710), and it also flipped both models.

**2. Both features are classic proxies.** Capital gain encodes access to investable assets, which is unevenly distributed by race and generational wealth. Marital status is a well-documented proxy for gender in this dataset.

**3. A gap in traceability isn't a gap in accountability.** Matthias's (2004) responsibility gap is real: no single person wrote this decision. But:
- **The data provider** is responsible for the bias the data carries in.
- **The developer** is responsible for relying on these features without auditing their effect on protected groups.
- **The system** can't be responsible, because it has no judgment, intent or ability to remedy anything. Blaming it turns avoidable human choices into an appearance of technical inevitability.

**4. Explainability is necessary but not sufficient.** Without knowing which inputs produced a harmful output, nobody can name what failed or contest it. But an attribution only describes the model's behavior. It doesn't explain the person's life, so accountability also needs institutional duties to act on what the explanation reveals.

## Skills demonstrated

- Local interpretability with counterfactuals and controlled single-feature experiments
- Proxy-discrimination detection on a standard fairness benchmark
- Separating statistical model behavior from causal claims
- Responsibility-gap analysis across developers, data providers and deployers

## Files

| File | Contents |
|---|---|
| [`Lab3_Feature_Attribution_Responsibility_Gap_Ravula.pdf`](./Lab3_Feature_Attribution_Responsibility_Gap_Ravula.pdf) | About 1,000 words: lab report and final argument, with five What-If Tool screenshots and an experiment table |

## Key sources

- Matthias, A. (2004). The responsibility gap. *Ethics and Information Technology, 6*(3), 175–183.
- Diakopoulos, N. (2016). Accountability in algorithmic decision making. *Communications of the ACM, 59*(2), 56–62.
- Lundberg, S. M., & Lee, S.-I. (2017). A unified approach to interpreting model predictions. *NeurIPS 30*.
- Rudin, C. (2019). Stop explaining black box machine learning models for high stakes decisions. *Nature Machine Intelligence, 1*, 206–215.
- Barocas, S., & Selbst, A. D. (2016). Big data's disparate impact. *California Law Review, 104*, 671–732.
