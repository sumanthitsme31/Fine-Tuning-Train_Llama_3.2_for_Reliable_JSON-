# Invoice Schema

**Required Keys:**
* `vendor` (string): The name of the vendor/company issuing the invoice.
* `invoice_number` (string): The unique identifier for the invoice.
* `date` (string): The date the invoice was issued, formatted as YYYY-MM-DD.
* `due_date` (string or null): The date payment is due (YYYY-MM-DD). Null if absent.
* `currency` (string): 3-letter ISO currency code (e.g., USD, EUR).
* `subtotal` (float): The total before taxes and discounts.
* `tax` (float or null): The total tax amount. Null if absent.
* `total` (float): The final total amount due.
* `line_items` (array of objects): Each object must contain `description` (string), `quantity` (float/int), and `unit_price` (float).
