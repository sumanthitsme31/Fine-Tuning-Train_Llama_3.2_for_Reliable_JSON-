# Purchase Order (PO) JSON Schema

This document defines the strict target structure for purchase order data extraction.

## Schema Definition

| Key | Data Type | Description | Format / Constraints | Handling if Absent |
| :--- | :--- | :--- | :--- | :--- |
| `buyer` | string | The name of the person or company purchasing the goods/services. | Plain text string. | Required. |
| `supplier` | string | The name of the vendor or company receiving the order. | Plain text string. | Required. |
| `po_number` | string | The unique reference number assigned to the purchase order. | Alphanumeric string. | Required. |
| `date` | string | The date the purchase order was created. | `YYYY-MM-DD`. | Required. |
| `delivery_date` | string | The requested or expected date of delivery. | `YYYY-MM-DD`. | `null` |
| `currency` | string | The currency used for the order. | 3-letter ISO code or common symbol. | Required. |
| `total` | float | The total value of the purchase order. | Numeric value. | Required. |
| `items` | array | A list of items being ordered. | Array of objects. | Required. |

### Item Object Structure
Each object within the `items` array must contain:
- `item_name` (string): The name of the item.
- `quantity` (float): Number of units ordered.
- `unit_price` (float): Price per unit.

## Strict Requirements
1. **Format:** Single valid JSON object only.
2. **Types:** Strings for names/dates, floats for numbers.
3. **Nulls:** Use `null` for missing optional fields like `delivery_date`.
