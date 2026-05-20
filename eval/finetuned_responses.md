# Fine-Tuned Responses
*(Responses truncated for readability)*

**doc_01.txt**
{"vendor": "Acme", "invoice_number": "123", "date": "2024-01-01", "due_date": null, "currency": "USD", "subtotal": 100.0, "tax": 10.0, "total": 110.0, "line_items": [{"description": "Widget", "quantity": 1, "unit_price": 100.0}]}

**doc_02.txt**
{"vendor": "Tech", "invoice_number": "102", "date": "2024-01-05", "due_date": null, "currency": "USD", "subtotal": 50.0, "tax": null, "total": 50.0, "line_items": [{"description": "Cable", "quantity": 5, "unit_price": 10.0}]}

**doc_03.txt** (Failure: missing items)
{"buyer": "Global", "supplier": "FastParts", "po_number": "111", "date": "2024-02-01", "delivery_date": null, "currency": "USD", "total": 500.0}

**doc_07.txt** (Failure: wrong date format)
{"vendor": "Corp", "invoice_number": "999", "date": "04/15/2024", "due_date": null, "currency": "USD", "subtotal": 200.0, "tax": 20.0, "total": 220.0, "line_items": [{"description": "Service", "quantity": 1, "unit_price": 200.0}]}

*(... 16 more clean JSON outputs matching the updated scores in finetuned_scores.csv ...)*