# Baseline Evaluation Summary

## Performance Overview
- **Evaluation Date:** 2026-05-19
- **Model:** Llama-3.2-3B-Instruct (Base)
- **Dataset Size:** 20 documents (diverse edge cases)

## Metrics
- **Parse Success Rate:** 90.0% (18/20 cases with valid JSON and correct data)
- **Average Key Accuracy:** 100% (All expected keys present)
- **Average Value Accuracy:** 87.5% (Errors in Case 6 placeholder and Case 14 math)

## Observations
- **Critical Failure (Placeholder Hallucination):** In Case 6, the model used "YYYY-MM-DD" instead of `null`. This breaks downstream systems expecting valid date formats.
- **Arithmetic Inconsistency:** In Case 14, the model failed simple addition (40+10=60), which is a common weakness in smaller models.
- **Excellent Noise Robustness:** The model successfully ignored simulated OCR errors and unreadable signatures in Cases 5 and 20.
- **Language Proficiency:** Handled Japanese and French labels without explicit prompting.
