# Invoice Schema
Defines the structure for extracting data from invoices.

| Key | Type | Description | Format |
| :--- | :--- | :--- | :--- |
| **vendor** | string | Name of the selling entity. | Plain text. |
| **invoice_number** | string | Unique identifier for the document. | Alpha-numeric as found. |
| **date** | string | Issuance date of the invoice. | YYYY-MM-DD |
| **due_date** | string/null | Date payment is expected. | YYYY-MM-DD or null if missing. |
| **currency** | string | 3-letter currency code. | ISO 4217 (USD, EUR, etc.) |
| **subtotal** | float | Amount before taxes. | Float (e.g., 100.0) |
| **tax** | float/null | Tax amount. | Float or null if not present. |
| **total** | float | Final amount to be paid. | Float. |
| **line_items** | array | List of products/services. | Array of objects. |

**line_items object:**
- `description` (string): Name/details of the item.
- `quantity` (integer): Number of units.
- `unit_price` (float): Price per unit.
