# esg-sentiment-xai

**Transparent, explainable sentiment analysis on ESG-related financial text.**

A prototype pipeline for extracting ESG signals directly from source documents — using a domain-specific financial NLP model and SHAP explainability — rather than relying on opaque third-party ESG scores.

Built as part of preparation for PhD research in Responsible and Interpretable AI at Ulster University.

---

## Why this exists

Berg et al. (2022) showed that ESG ratings from major agencies diverge significantly due to methodological opacity. Most ESG-aligned investment frameworks either use these inconsistent third-party scores as a black box, or apply ESG as a post-hoc filter after portfolio optimisation.

This prototype takes a different approach — extracting ESG sentiment signals **directly from source documents** (news headlines, sustainability reports, regulatory filings) using a model trained on financial language, and making every prediction **explainable at the word level** using SHAP.

That's the white-box principle: explainability by design, not post-hoc patching.

---

## What it does

- Classifies ESG-related text as **positive**, **negative**, or **neutral**
- Uses a **domain-specific financial NLP model** — more accurate on financial text than general-purpose BERT
- Generates **SHAP word-level explanations** — shows exactly which words drove each prediction
- Covers all three ESG dimensions: Environmental, Social, Governance
- Outputs charts and a CSV of results

---

## Research relevance

| This prototype | PhD Sub-theme I contribution |
|---|---|
| Domain-specific financial NLP | More accurate ESG signal extraction than general BERT |
| Extracts from source documents | Reduces dependency on opaque third-party scores |
| SHAP word-level explanations | White-box explainability by design |
| Lightweight and deployable | No heavy GPU requirements |
| Cross-domain architecture | Same pipeline adapts to Sub-theme II health self-reports |

---

## Quick start

```bash
# Clone the repo
git clone https://github.com/your-username/esg-sentiment-xai.git
cd esg-sentiment-xai

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook

# Open esg_sentiment_analyser.ipynb and run cells in order
```

---

## Output examples

```
[Environmental] POSITIVE (91.3%)
  "Company reduces carbon emissions by 40% ahead of 2030 target"
  Scores: positive: 91.3% | negative: 3.1% | neutral: 5.6%

[Governance] NEGATIVE (94.7%)
  "CEO ousted after board discovers undisclosed conflicts of interest"
  Scores: positive: 1.2% | negative: 94.7% | neutral: 4.1%
```

SHAP explanation shows which specific words drove each prediction — making the reasoning visible, auditable, and challengeable.

---

## Tech stack

| Component | Tool |
|---|---|
| NLP model | distilroberta-finetuned-financial-news-sentiment-analysis |
| Explainability | SHAP |
| Framework | PyTorch + HuggingFace Transformers |
| Language | Python 3.10 |
| Notebook | Jupyter |

---

## Next steps — PhD roadmap

1. Scale to full sustainability reports and regulatory filings
2. Integrate ESG sentiment scores as causal features in portfolio optimisation
3. Apply causal inference — DAGs and do-calculus — to model WHY ESG sentiment affects portfolio risk
4. Extend pipeline to Sub-theme II — mood journal NLP for women's health platform
5. Fairness evaluation across firm types and demographic groups

---

## References

Berg, F., Kölbel, J. F., & Rigobon, R. (2022). Aggregate Confusion: The Divergence of ESG Ratings. *Review of Finance*, 26(6), 1315–1344.

Araci, D. (2019). FinBERT: Financial Sentiment Analysis with Pre-trained Language Models. *arXiv:1908.10063*.

Lundberg, S. M., & Lee, S. I. (2017). A Unified Approach to Interpreting Model Predictions. *NeurIPS 2017*.

---

*Author: Hima — Applied AI Scientist*
*PhD research — Ulster University (in progress)*
*Responsible and Interpretable AI for Sustainable Finance and Wellbeing Technologies*
