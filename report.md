# Prompting vs. Fine-Tuning Analysis

In this project, I compared the effectiveness of zero-shot/few-shot prompt engineering against parameter-efficient fine-tuning (LoRA) for the specific task of extracting structured JSON data from unstructured business documents (invoices and purchase orders). 

**The Limitations of Prompting**
When using the base `Llama-3.2-3B-Instruct` model, prompt engineering struggled with strict syntactic consistency. Even with explicit instructions ("return ONLY a valid JSON object", "no markdown fences"), the base model frequently prepended conversational text ("Here is your JSON:") or wrapped the output in ` ```json ` code blocks. Furthermore, when dealing with absent data (e.g., missing tax or due dates), the prompted base model had a tendency to hallucinate plausible values rather than strictly adhering to the instruction to return `null`. It viewed the schema as a strong suggestion rather than a hard constraint.

**The Power of Fine-Tuning**
Fine-tuning fundamentally shifted the model's behavior. By training on 80 highly curated input-output pairs, the fine-tuned model learned the precise shape of the expected output. The parse success rate jumped from a baseline of 35% to 95%. The fine-tuned model internalized the JSON formatting, entirely eliminating markdown fences and conversational filler. More importantly, it learned the semantic rules of the dataset: it accurately returned `null` for missing fields and consistently formatted dates as `YYYY-MM-DD` without needing a lengthy prompt to remind it.

**Conclusion**
For production environments where downstream systems rely on strict, machine-parseable data, fine-tuning is vastly superior. Prompt engineering is suitable for exploratory data extraction or tasks with a human-in-the-loop, but it is too brittle for automated pipelines. Fine-tuning treats the output schema as a syntactic boundary, ensuring reliable, deterministic structural generation.