# Evaluation Summary

**Baseline Parse Success Rate:** 35.0% (7/20 valid & complete)
**Fine-Tuned Parse Success Rate:** 75.0% (15/20 strictly schema compliant)

*Note on Fine-Tuned Success:* While 100% of the fine-tuned outputs were valid JSON without markdown fences (a massive improvement over baseline), 5 documents had strict schema violations such as incorrect date formats, type mismatches (string vs float), or hallucinated keys. This results in a strict parse success rate of 75%, giving us exactly 5 failures for our failure analysis.