# AI-ML-Assignment-8-LLM-Evaluation

**Name:** Denniz Garza
**Task / Model:** Sentiment Classification — fine-tuned `distilbert-base-uncased` with LoRA

---

## Repository Contents
- `FineTuning_Evaluation_Week8.ipynb` — Jupyter Notebook with evaluation code, metrics calculation, confusion matrix generation, and error analysis.
- `confusion_matrix.png` — Normalized confusion matrix visualization (saved from the notebook).
- `requirements.txt` — Python dependencies.
- `README.md` — This file.

---

## Final Evaluation Metrics (Test Set)

| Metric                 | Value        |
|-----------------------:|:------------:|
| Accuracy               | 0.5080       |
| Precision (Macro)      | 0.2540       |
| Recall (Macro)         | 0.5000       |
| F1-Score (Macro)       | 0.3369       |

---

## Metric Justification: Why F1-Score (Macro) is the primary metric

Accuracy measures overall correctness but can be misleading under class imbalance — a naïve model predicting the dominant class can have high accuracy while failing to detect minority classes. **F1-Score (Macro)** averages the harmonic mean of precision and recall across all classes equally, ensuring the model’s ability to identify minority classes (recall) and avoid false positives (precision) is reflected. For balanced, fair evaluation across classes — especially when class sizes differ — Macro F1 gives a more actionable measure of real-world performance than raw accuracy.

---

## Error Analysis Summary

**Worst-performing class:** `LABEL_1`  
**Observed F1 (class):** `0.0000`

**Misclassified example 1 (true → predicted):**  
> Text: "When I unsuspectedly rented A Thousand Acres, I thought I was in for an entertaining King Lear story and of course Michelle Pfeiffer was in it, so what could go wrong? Very quickly, however, I realized that this story was about A Thousand Other Things besides just Acres. I sta..."  
**Likely cause:** Ambiguous phrasing / sarcasm / domain-specific vocabulary / truncated context.

**Misclassified example 2 (true → predicted):**  
> Text: "This is the latest entry in the long series of films with the French agent, O.S.S. 117 (the French answer to James Bond). The series was launched in the early 1950's, and spawned at least eight films (none of which was ever released in the U.S.). 'O.S.S.117:Cairo,Nest Of Spies' is a breezy little co..."  
**Likely cause:** Label noise / contextual dependency not present in training data.

---

## Youtube Link
