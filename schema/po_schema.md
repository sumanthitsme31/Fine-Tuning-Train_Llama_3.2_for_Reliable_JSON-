# Purchase Order Schema
Defines the structure for extracting data from purchase orders.

| Key | Type | Description | Format |
| :--- | :--- | :--- | :--- |
| **buyer** | string | Entity purchasing the goods. | Plain text. |
| **supplier** | string | Entity providing the goods. | Plain text. |
| **po_number** | string | Unique PO identifier. | Alpha-numeric. |
| **date** | string | Date the PO was created. | YYYY-MM-DD |
| **delivery_date** | string/null | Expected delivery date. | YYYY-MM-DD or null. |
| **currency** | string | Currency for the transaction. | ISO 4217 code. |
| **total** | float | Total value of the order. | Float. |
| **items** | array | List of items being ordered. | Array of objects. |

**items object:**
- `item_name` (string): Name of the product.
- `quantity` (integer): Number of units.
- `unit_price` (float): Price per unit.
