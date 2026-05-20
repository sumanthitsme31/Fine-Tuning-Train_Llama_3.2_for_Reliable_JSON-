# Prompt Evaluation

Testing the best prompt (Version 3) against the 3 worst-performing baseline documents (doc_01, doc_02, doc_15).

**Results:**
1. **doc_01:** Prompt V3 successfully removed the markdown fences and extracted the JSON perfectly.
2. **doc_02:** Prompt V3 removed the prose preamble, but hallucinated a `tax` value of `0.0` instead of returning `null` as explicitly instructed.
3. **doc_15:** Prompt V3 failed to drop the markdown fences entirely, outputting raw JSON but appending a trailing `}` character that broke the parser.

**Conclusion:**
While heavy prompt engineering (V3) improved the baseline significantly, it still failed to achieve 100% syntactic reliability on the hardest documents. The model's inherent chat-alignment makes it stubbornly resistant to outputting pure, raw code without markdown in edge cases. Fine-tuning completely bypasses this issue.