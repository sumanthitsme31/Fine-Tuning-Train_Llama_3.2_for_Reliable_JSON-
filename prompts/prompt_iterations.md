# Prompt Iterations

## Version 1 (Zero-Shot)
"Extract the data from this invoice into JSON format."
*Result:* Hallucinated keys, included markdown fences, failed to parse.

## Version 2 (Few-Shot + Strict Instruction)
"Extract the following invoice into JSON. Use exactly these keys: vendor, invoice_number, date, due_date, currency, subtotal, tax, total, line_items. Do not include markdown. Do not include introductory text."
*Result:* Removed introductory text, but still occasionally included ```json blocks. Replaced missing fields with "N/A" instead of `null`.

## Version 3 (Few-Shot + Schema Definition + Null Enforcement)
"You are a strict JSON data extractor. Extract the invoice into the following JSON schema. If a value is missing, you MUST output null, not a string. Output ONLY raw JSON, no code fences. Schema: [Schema details here]."
*Result:* Best performance. Handled `null` much better, but still occasionally broke formatting on complex line items.