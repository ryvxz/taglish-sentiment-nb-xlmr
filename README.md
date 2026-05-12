# Sentiment Analysis of Taglish E-Commerce Reviews using Naive Bayes and XLM-RoBERTa

A comparative study of a classical generative classifier (Multinomial Naive Bayes) and a state-of-the-art contextual transformer (XLM-RoBERTa) on three-class sentiment classification of Filipino-English code-switched product reviews. Beyond reporting accuracy, this project investigates what each model "sees" and where each fails — examining top predictive features, attention patterns, and error distributions across linguistic phenomena specific to Taglish (pragmatic markers, negation, slang, code-switching density).

## Authors

| Name | Role | Key Contributions |
|------|------|-------------------|
| Jodimeer A. Ammang | XLM-R Lead | Notebooks 03 & 04; Sections 4.2, 5.3, 5.4, 6.2, 6.3, 7, 8 |
| Joaquim Cruz | Classical Model Lead | Notebooks 01 & 02; Sections 4.1, 5.1, 5.2, 6.1 |
| Dan Angelo Erasquin | Manuscript Lead | Manuscript structure and editorial integration; comparison analysis |
| Justin Floro | Data & EDA Lead | Dataset pipeline, EDA visualizations, phenomenon slices |

**Course:** Machine Learning (CS ELEC 2C) — 3CSE, Group 5

## Dataset

This project uses **FiReCS** (Filipino-English Reviews, Code-Switched) — 10,487 human-annotated reviews from Shopee Philippines and Google Maps, sourced from:

> Cosme, C. J., & De Leon, M. M. (2024). *Sentiment analysis of Code-Switched Filipino-English product and service reviews using Transformers-Based large language models.*

The dataset is split 70/30 (7,340 train / 3,147 test, stratified) to match the original study. Labels are Positive, Negative, and Neutral, assigned by three native Filipino-speaking annotators (Krippendorff's α = 0.83).

**To obtain FiReCS:** The dataset is associated with the Cosme & De Leon (2024) Springer chapter. Contact the original authors or access through the thesis team's existing copy. The CSV is not included in this repository due to size.

## How to Reproduce Results

All experiments run on **Google Colab**. No local setup is required.

1. Upload the contents of this repository to a Google Drive folder (e.g., `MyDrive/taglish-project/`).
2. Place `firecs.csv` in the `data/` subfolder.
3. Open `3CSE_Group5_Implementation.ipynb` in Google Colab.
4. Set the runtime to **T4 GPU** (Runtime → Change runtime type → T4 GPU).
5. Edit the `DRIVE_BASE` path variable in the setup cell if your folder path differs.
6. Run all cells top-to-bottom (Runtime → Run all).

This compiled notebook contains the full pipeline — data loading, preprocessing, EDA, Naive Bayes training and evaluation, XLM-RoBERTa fine-tuning, and the comparative analysis (McNemar's test, phenomenon-sliced error analysis). Fine-tuning takes approximately 7 minutes on a Tesla T4.

The individual stage notebooks (`01_data_and_eda.ipynb` through `04_comparison.ipynb`) are also included in `notebooks/` for reference.

## Results Summary

| Metric | Naive Bayes | XLM-RoBERTa |
|--------|-------------|-------------|
| Accuracy | 0.7909 | 0.8306 |
| Weighted F1 | 0.7928 | 0.8319 |
| Negative F1 | 0.7885 | 0.8471 |
| Neutral F1 | 0.7248 | 0.7696 |
| Positive F1 | 0.8685 | 0.8874 |

McNemar's test confirms the difference is statistically significant (χ² = 31.32, p < 0.001). XLM-RoBERTa's largest advantages appear on low code-switching density reviews (+8.3 pp) and Taglish negation constructions (+6.3–7.3 pp), while the gap narrows on high-frequency pragmatic markers like *na* (+2.7 pp).

## Repository Structure

```
├── README.md
├── requirements.txt
├── .gitignore
├── LLM_USAGE.md
├── 3CSE_Group5_Implementation.ipynb       ← start here
├── notebooks/
│   ├── 01_data_and_eda.ipynb
│   ├── 02_naive_bayes.ipynb
│   ├── 03_xlmr_finetune.ipynb
│   └── 04_comparison.ipynb
├── results/
│   ├── figures/
│   │   ├── eda_class_distribution.png
│   │   ├── eda_length_distribution.png
│   │   ├── nb_confusion_matrix.png
│   │   ├── nb_top_features.png
│   │   ├── xlmr_confusion_matrix.png
│   │   ├── xlmr_attention_examples.png
│   │   ├── agreement_matrix.png
│   │   └── phenomenon_slice_comparison.png
│   ├── nb_predictions.csv
│   ├── xlmr_predictions.csv
│   ├── phenomenon_slices.csv
│   └── xlmr_training_metadata.json
└── manuscript/
    ├── 3CSE_Group5_Manuscript.pdf
    └── 3CSE_Group5_Implementation.pdf
```

## LLM Usage Disclosure

All notebook code was drafted with Claude (Anthropic) assistance, then reviewed and executed by team members. All manuscript sections were drafted with Claude assistance using actual experimental outputs, then reviewed and edited by authors. Full details are in [`LLM_USAGE.md`](LLM_USAGE.md).

## References

- Cosme, C. J., & De Leon, M. M. (2024). Sentiment analysis of Code-Switched Filipino-English product and service reviews using Transformers-Based large language models.
- Conneau, A., et al. (2020). Unsupervised Cross-lingual Representation Learning at Scale.
- Salve, H. N., & Tubil, P. N. T. (2025). Bilingual Code-Switching Using XLM-RoBERTa.
- Mao, Y., Liu, Q., & Zhang, Y. (2024). Sentiment analysis methods, applications, and challenges: A systematic literature review.

## License

This project is for academic purposes (CS ELEC 2C, Machine Learning). The FiReCS dataset is property of its original authors.