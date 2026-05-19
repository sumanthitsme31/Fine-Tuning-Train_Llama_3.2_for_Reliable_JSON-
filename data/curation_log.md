# Curation Log
Tracking the selection of training examples for fine-tuning.

| example_id | document_type | source | kept_or_rejected | reason |
| :--- | :--- | :--- | :--- | :--- |
| 1-10 | invoice | Synthetic Mix | KEPT | Diverse layouts for standard retail. |
| 11-20 | invoice | CORD v2 | KEPT | Real-world receipt noise handling. |
| 21-35 | invoice | Synthetic Edge | KEPT | Missing date/tax fields (Testing null). |
| 36-50 | invoice | Multi-Line | KEPT | Testing large line_items arrays. |
| 51-80 | PO | Synthetic PO | KEPT | Diverse PO layouts with item arrays. |
