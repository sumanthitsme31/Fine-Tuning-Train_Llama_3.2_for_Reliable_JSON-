# Failure Analysis 02

## Source Document Text
PURCHASE ORDER
Buyer: Global Industries
Supplier: FastParts
Date: 2024-03-01
Total: 1000.00
Items:
1. Gear box - 10 - 50.00
2. Motor - 5 - 100.00
[Page Break]
3. Bearings - 100 - 0.00 (Promo)

## Expected JSON Output
`{"buyer": "Global Industries", "supplier": "FastParts", "po_number": null, "date": "2024-03-01", "delivery_date": null, "currency": "USD", "total": 1000.0, "items": [{"item_name": "Gear box", "quantity": 10, "unit_price": 50.0}, {"item_name": "Motor", "quantity": 5, "unit_price": 100.0}, {"item_name": "Bearings", "quantity": 100, "unit_price": 0.0}]}`

## Model's Incorrect Output
`{"buyer": "Global Industries", "supplier": "FastParts", "po_number": null, "date": "2024-03-01", "delivery_date": null, "currency": "USD", "total": 1000.0}`

## What went wrong
The model completely missed the `items` array. `has_all_required_keys` = False.

## Why it likely failed
The PO contains a page break artifact `[Page Break]` in the middle of the items list, which confused the model. The training dataset lacked examples of messy, multi-page layout artifacts interrupting arrays.

## What training data change would fix it
Add 5-10 synthetic examples where line items are interrupted by `\nPage 2\n` or `[Page Break]` tags, but where the target JSON still correctly aggregates all items into the single array.