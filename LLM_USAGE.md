# LLM Usage Disclosure

This document lists all artifacts in this project where a Large Language Model (Claude, Anthropic) was used, the team member responsible, and the level of assistance involved.

**Assistance levels:**
- **drafted** — LLM produced the first draft; author reviewed, edited, and verified all content
- **edited** — Author wrote the content; LLM copy-edited for grammar and clarity
- **reviewed-only** — LLM reviewed for bugs or logical errors; author wrote and understood all content

---

## Notebooks

| Artifact | Author | Assistance Level | Description |
|----------|--------|-----------------|-------------|
| `01_data_and_eda.ipynb` | Justin Floro | drafted | LLM drafted preprocessing pipeline and EDA cells; author reviewed, ran, and verified all outputs |
| `02_naive_bayes.ipynb` | Joaquim Cruz | drafted | LLM drafted NB training, hyperparameter sweep, and top-feature extraction cells; author reviewed, ran, and verified all outputs |
| `03_xlmr_finetune.ipynb` | Jodimeer Ammang | drafted | LLM drafted fine-tuning loop, evaluation, and attention visualization cells; author reviewed, ran, and verified all outputs |
| `04_comparison.ipynb` | Dan Angelo Erasquin | drafted | LLM drafted agreement matrix, McNemar's test, and phenomenon-slice analysis cells; author reviewed, ran, and verified all outputs |
| `3CSE_Group5_Implementation.ipynb` | All members | drafted | Compiled notebook assembled from the four above; LLM assisted in merging and sequencing cells; all members reviewed the final run |

---

## Manuscript

| Artifact | Author | Assistance Level | Description |
|----------|--------|-----------------|-------------|
| Abstract | Dan Angelo Erasquin | edited | Author drafted using final experimental numbers; LLM copy-edited for clarity |
| Introduction | Dan Angelo Erasquin | edited | Author drafted motivation and research questions; LLM copy-edited for grammar |
| Related Work | Dan Angelo Erasquin | reviewed-only | Author wrote all summaries from source papers; LLM reviewed for coherence |
| Model & Algorithm — NB (§4.1) | Joaquim Cruz | drafted | LLM drafted NB derivation and assumption discussion; author verified all equations and interpretations |
| Model & Algorithm — XLM-R (§4.2) | Jodimeer Ammang | drafted | LLM drafted XLM-R architecture and fine-tuning rationale; author verified all technical claims |
| Implementation (§5) | Justin Floro | edited | Author wrote preprocessing and hyperparameter details; LLM copy-edited for clarity |
| Results — NB (§6.1) | Joaquim Cruz | drafted | LLM drafted results narrative using actual output numbers; author verified all figures and tables |
| Results — XLM-R (§6.2) | Jodimeer Ammang | drafted | LLM drafted results narrative using actual output numbers; author verified all figures and tables |
| Results — Comparison (§6.3) | Jodimeer Ammang | drafted | LLM drafted comparison narrative including McNemar's result and phenomenon-slice table; author verified all values |
| Discussion (§7) | Jodimeer Ammang | drafted | LLM drafted interpretations of model behavior; all interpretations reviewed and defended by authors |
| Conclusion (§8) | Jodimeer Ammang | edited | Author wrote summary and future directions; LLM copy-edited for clarity |
| References | All members | reviewed-only | Authors compiled references from source papers; LLM reviewed for formatting consistency |

---

## Other

| Artifact | Author | Assistance Level | Description |
|----------|--------|-----------------|-------------|
| `README.md` | Dan Angelo Erasquin | drafted | LLM drafted based on project documentation; author reviewed and verified all content |
| `LLM_USAGE.md` | Dan Angelo Erasquin | drafted | LLM drafted based on team's actual usage; author reviewed and verified all entries |

---

*All experimental results, numbers, figures, and tables were produced by running the notebooks on the actual FiReCS dataset. No LLM was used to generate, fabricate, or estimate any result.*
