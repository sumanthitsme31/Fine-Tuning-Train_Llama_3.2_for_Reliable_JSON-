# Post Fine-Tuning Evaluation Responses

This file contains the verbatim, raw output from the fine-tuned `llama3_invoice_v2` model.

---

## Response 14 - Gas Station (Post-FT)
**Model Output:**
```json
{"vendor": "GAS STATION #5", "total": "50.00", "Fuel": "40.00", "Car Wash": "10.00", "Balance Due": "50.00"}
```
**Status:** SUCCESS (Corrected previous math error of 60.0).

## Response 06 - Cash Receipt (Post-FT)
**Model Output:**
```json
{"vendor": "Unknown", "date": "Unknown", "total": "20.00", "TEXT": "CASH RECEIPT", "Items": {"Hammer": "$15", "Nails": "$5"}}
```
**Status:** IMPROVED (Stopped hallucinating fake date, though used "Unknown" instead of null).
