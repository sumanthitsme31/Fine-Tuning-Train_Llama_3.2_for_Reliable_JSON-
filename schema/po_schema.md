# Purchase Order Schema

**Required Keys:**
* `buyer` (string): The name of the entity purchasing the goods/services.
* `supplier` (string): The name of the entity supplying the goods/services.
* `po_number` (string): The unique purchase order identifier.
* `date` (string): The date the PO was created, formatted as YYYY-MM-DD.
* `delivery_date` (string or null): The expected delivery date (YYYY-MM-DD). Null if absent.
* `currency` (string): 3-letter ISO currency code (e.g., USD, EUR).
* `total` (float): The total value of the purchase order.
* `items` (array of objects): Each object must contain `item_name` (string), `quantity` (float/int), and `unit_price` (float).
