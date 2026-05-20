# Curation Log

| example_id | document_type | source | kept_or_rejected | reason | schema_issues_found |
|---|---|---|---|---|---|
| 001 | Invoice | CORD v2 | Kept | Clear layout, standard fields. | None |
| 002 | Invoice | CORD v2 | Kept | Multi-item, uses EUR currency. | Date was 15 Jan, normalized to YYYY-MM-DD. |
| 003 | PO | Synthetic | Kept | Standard PO structure. | None |
| 004 | Invoice | SROIE | Kept | Missing tax and due date. Good test for `null` handling. | Ensure tax is null, not 0. |
| 005 | PO | DocVQA | Kept | GBP currency, missing delivery date. | None |
| 006 | PO | DocVQA | Rejected | Illegible item prices. | Ambiguous ground truth. |
