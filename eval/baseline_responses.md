# Baseline Evaluation Responses

This file contains the verbatim, raw output from the pre-trained Llama-3.2-3B-Instruct model for 20 evaluation documents.

---

## Response 01 - Starbucks
**Model Output:**
```json
{
  "vendor_name": "STARBUCKS COFFEE #1234",
  "date": "2026-05-15",
  "items": [
    {"name": "Caramel Macchiato", "price": 5.5},
    {"name": "Blueberry Muffin", "price": 3.75}
  ],
  "total": 9.25
}
```

## Response 02 - Global Logistics
**Model Output:**
```json
{
  "vendor_name": "GLOBAL LOGISTICS LTD.",
  "invoice_no": "PO-998-X",
  "total": 1250.5
}
```

## Response 03 - Apple Services
**Model Output:**
```json
{
  "vendor": "Apple Services",
  "invoice_date": "2026-05-01",
  "due_date": "2026-05-15",
  "total": 9.99
}
```

## Response 04 - Cafe de Paris
**Model Output:**
```json
{
  "vendor": "CAFE DE PARIS",
  "total": 7.5,
  "currency": "€"
}
```

## Response 05 - Walmart Noise
**Model Output:**
```json
{
  "vendor": "WALMART STORE 554",
  "total": 142.1
}
```

## Response 06 - Cash Receipt (Missing Date)
**Model Output:**
```json
{
  "vendor": "CASH RECEIPT",
  "date": "YYYY-MM-DD",
  "total": 20.0
}
```

## Response 07 - Best Buy
**Model Output:**
```json
{
  "vendor": "BEST BUY",
  "subtotal": 100.0,
  "tax": 8.0,
  "total": 108.0
}
```

## Response 08 - Pizza Kitchen
**Model Output:**
```json
{
  "vendor_name": "THE ORIGINAL AND AUTHENTIC NEW YORK PIZZA KITCHEN & DELI INC.",
  "total": 22.5
}
```

## Response 09 - Tokyo Sushi
**Model Output:**
```json
{
  "vendor": "TOKYO SUSHI",
  "total": 45.0,
  "date": "2026-06-12"
}
```

## Response 10 - Nike Store
**Model Output:**
```json
{
  "vendor": "NIKE STORE",
  "total": 96.0
}
```

## Response 11 - Whole Foods
**Model Output:**
```json
{
  "vendor": "WHOLE FOODS",
  "items": [
    {"name": "Organic Milk", "qty": 2, "price": 4.99},
    {"name": "Bread", "qty": 1, "price": 3.5}
  ],
  "total": 13.48
}
```

## Response 12 - NY Diner
**Model Output:**
```json
{
  "vendor": "NEW YORK DINER",
  "subtotal": 50.0,
  "tip": 10.0,
  "total": 64.5
}
```

## Response 13 - Kwik-E-Mart
**Model Output:**
```json
{
  "vendor": "KWIK-E-MART",
  "address": "742 Evergreen Terrace, Springfield",
  "total": 15.2
}
```

## Response 14 - Gas Station (Math Fail)
**Model Output:**
```json
{
  "vendor": "GAS STATION #5",
  "total": 60.0
}
```

## Response 15 - Mixed Date Format
**Model Output:**
```json
{
  "date_iso": "2026-05-12"
}
```

## Response 16 - Plumbing Pros
**Model Output:**
```json
{
  "service": "Fixed Leak",
  "hours": 2.5,
  "rate": 80.0,
  "total": 200.0
}
```

## Response 17 - Amazon Returns
**Model Output:**
```json
{
  "vendor": "AMAZON RETURNS",
  "type": "Refund",
  "amount": -45.0
}
```

## Response 18 - Hilton
**Model Output:**
```json
{
  "hotel": "HILTON",
  "room_tax": 20.0,
  "city_tax": 5.0,
  "total": 225.0
}
```

## Response 19 - Bad Math Shop
**Model Output:**
```json
{
  "vendor": "BAD MATH SHOP",
  "items_sum": 20.0,
  "stated_total": 30.0
}
```

## Response 20 - McDonald's Messy
**Model Output:**
```json
{
  "vendor": "McDonald's",
  "total": 5.99
}
```
