# Failure Analysis 03

## Source Document Text
INVOICE
Vendor: Corp LLC
Date: 04/15/2024
Total: 500
Due: Upon Receipt
Items: 1 Service - 500

## Expected JSON Output
`{"vendor": "Corp LLC", "invoice_number": null, "date": "2024-04-15", "due_date": null, "currency": "USD", "subtotal": 500.0, "tax": null, "total": 500.0, "line_items": [{"description": "Service", "quantity": 1, "unit_price": 500.0}]}`

## Model's Incorrect Output
`{"vendor": "Corp LLC", "invoice_number": null, "date": "04/15/2024", "due_date": null, "currency": "USD", "subtotal": 500.0, "tax": null, "total": 500.0, "line_items": [{"description": "Service", "quantity": 1, "unit_price": 500.0}]}`

## What went wrong
The model output the date as `04/15/2024` instead of formatting it to `YYYY-MM-DD`.

## Why it likely failed
The base Llama 3.2 model has a strong bias towards standard US date formats when reading them directly from text. The fine-tuning dataset did not have enough examples demonstrating the active conversion from `MM/DD/YYYY` text to `YYYY-MM-DD` JSON values.

## What training data change would fix it
Add 10 more invoices with explicit US date formats (MM/DD/YYYY, or "April 15th, 2024") in the raw text, specifically mapped to strict `YYYY-MM-DD` strings in the target output.