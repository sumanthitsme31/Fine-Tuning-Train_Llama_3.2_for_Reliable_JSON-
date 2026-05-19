# Invoice JSON Schema

This document defines the strict target structure for invoice data extraction. Every model response must conform to this schema to be considered valid.

## Schema Definition

| Key | Data Type | Description | Format / Constraints | Handling if Absent |
| :--- | :--- | :--- | :--- | :--- |
| `vendor` | string | The legal name of the company or entity issuing the invoice. | Plain text string. | Required. |
| `invoice_number` | string | The unique identifier assigned by the vendor to the invoice. | Alphanumeric string. | Required. |
| `date` | string | The date the invoice was issued. | `YYYY-MM-DD` (e.g., 2024-03-15). | Required. |
| `due_date` | string | The date by which payment is expected. | `YYYY-MM-DD` (e.g., 2024-04-15). | `null` |
| `currency` | string | The 3-letter ISO 4217 code for the currency used. | 3-letter uppercase (e.g., USD, EUR, GBP). | Required. |
| `subtotal` | float | The total amount before taxes and additional fees. | Numeric value (e.g., 1200.50). | Required. |
| `tax` | float | The calculated tax amount (VAT, Sales Tax, etc.). | Numeric value. | `null` |
| `total` | float | The final amount due including taxes and fees. | Numeric value. | Required. |
| `line_items` | array | A list of products or services billed in the invoice. | Array of objects. | Required (empty `[]` if none). |

### Line Item Object Structure
Each object within the `line_items` array must contain:
- `description` (string): The name or description of the service/product.
- `quantity` (float): The number of units provided.
- `unit_price` (float): The price per single unit.

## Strict Requirements
1. **Format:** Output must be a single, valid JSON object.
2. **No Proamble:** No "Here is the JSON" or markdown code fences (unless specified in prompt).
3. **Data Types:** Ensure numbers are not wrapped in quotes (e.g., `100.0`, not `"100.0"`).
4. **Dates:** Always normalize dates to `YYYY-MM-DD`.
