# Failure Analysis 01

## Source Document Text
PURCHASE ORDER
From: Company C
To: Company D
Order Number: 9911
Date: 2024-06-01
Total: $500
Items: 10x Chair @ 50

## Expected JSON Output
`{"buyer": "Company C", "supplier": "Company D", "po_number": "9911", "date": "2024-06-01", "delivery_date": null, "currency": "USD", "total": 500.0, "items": [{"item_name": "Chair", "quantity": 10, "unit_price": 50.0}]}`

## Model's Incorrect Output
`{"buyer": "Company C", "supplier": "Company D", "po_num": "9911", "date": "2024-06-01", "delivery_date": null, "currency": "USD", "total": 500.0, "items": [{"item_name": "Chair", "quantity": 10, "unit_price": 50.0}]}`

## What went wrong
The model used the key `po_num` instead of the schema-required `po_number`.

## Why it likely failed
The source document uses "Order Number". In the training data, there might not have been enough examples mapping generic terms like "Order Number" specifically to `po_number`, causing the model to slightly hallucinate the key name based on its pre-trained weights.

## What training data change would fix it
Add 3-5 more synthetic PO examples to the JSONL dataset where the raw text uses variations like "Order Number" and "PO#" and strictly map them to `po_number` in the target output.