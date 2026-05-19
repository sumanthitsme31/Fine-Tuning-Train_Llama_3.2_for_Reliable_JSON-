# Final Report: Prompting vs. Fine-Tuning

## Overview
This project compared the zero-shot capabilities of Llama 3.2 3B against a LoRA fine-tuned version for structured data extraction.

## Analysis
While Llama 3.2 is highly capable of understanding intent, it lacks "format discipline." During baseline testing, the model often hallucinated date formats (`YYYY-MM-DD`) and made basic arithmetic errors when summing invoice totals.

**Fine-tuning** solved the logic errors (math) and the formatting errors (preamble/markdown). However, for smaller models, the "system prompt" remains a critical partner to fine-tuning to ensure zero conversational overhead. For enterprise-grade reliability, fine-tuning is required to turn a "chatter" into a "data engine."
