# Failure Analysis 04

## Source Document Text
PURCHASE ORDER
Buyer: Corp Inc
Supplier: Inc Ltd
PO Number: 1234
Date: 2024-01-01
Total Amount: $1,500.00
Items: Hardware (1) - $1,500.00

## Expected JSON Output
`{"buyer": "Corp Inc", "supplier": "Inc Ltd", "po_number": "1234", "date": "2024-01-01", "delivery_date": null, "currency": "USD", "total": 1500.0, "items": [{"item_name": "Hardware", "quantity": 1, "unit_price": 1500.0}]}`

## Model's Incorrect Output
`{"buyer": "Corp Inc", "supplier": "Inc Ltd", "po_number": "1234", "date": "2024-01-01", "delivery_date": null, "currency": "USD", "total": "$1,500.00", "items": [{"item_name": "Hardware", "quantity": 1, "unit_price": 1500.0}]}`

## What went wrong
The model returned `"$1,500.00"` (a String) instead of `1500.0` (a Float) for the `total` field.

## Why it likely failed
The model copied the literal string with the dollar sign and comma separator instead of casting it to a float. This suggests the training data mostly had pre-cleaned numbers in the raw text (e.g., `1500.00`).

## What training data change would fix it
Include more examples in the JSONL training set with heavily formatted currency symbols and commas in the input text (e.g., `$1,500.00`, `€1.500,00`) mapped to strict float values (`1500.0`) in the output.