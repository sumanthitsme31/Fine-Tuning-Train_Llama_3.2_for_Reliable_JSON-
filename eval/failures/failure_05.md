# Failure Analysis 05

## Source Document Text
PURCHASE ORDER
Buyer: Bar Corp
Supplier: Baz LLC
PO Num: 8881
Date: 2024-02-02
Included Tax: $10
Total: 100
Items: Parts x10 = 100

## Expected JSON Output
`{"buyer": "Bar Corp", "supplier": "Baz LLC", "po_number": "8881", "date": "2024-02-02", "delivery_date": null, "currency": "USD", "total": 100.0, "items": [{"item_name": "Parts", "quantity": 10, "unit_price": 10.0}]}`

## Model's Incorrect Output
`{"buyer": "Bar Corp", "supplier": "Baz LLC", "po_number": "8881", "date": "2024-02-02", "delivery_date": null, "currency": "USD", "tax": 10.0, "total": 100.0, "items": [{"item_name": "Parts", "quantity": 10, "unit_price": 10.0}]}`

## What went wrong
The model hallucinated a `"tax": 10.0` field. 

## Why it likely failed
The Purchase Order schema does NOT have a `tax` key (unlike the Invoice schema). Because the word "Tax" appeared in the raw document text, the model reverted to Invoice-style generation and hallucinated the key to fit the data.

## What training data change would fix it
Add examples of Purchase Orders that explicitly mention taxes or shipping fees in the raw text, but strictly omit them from the JSON output, enforcing strict schema compliance for POs regardless of extra text details.