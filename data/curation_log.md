# Curation Log

| example_id | document_type | source | kept_or_rejected | reason | schema_issues_found |
|---|---|---|---|---|---|
| INV_01 | Invoice | CORD v2 | Kept | Standard layout. | None |
| INV_02 | Invoice | CORD v2 | Kept | Includes discount line. | Handled via unit_price negative float. |
| INV_03 | Invoice | CORD v2 | Kept | Missing due date. | Due date set to null. |
| INV_04 | Invoice | CORD v2 | Kept | GBP Currency. | Normalized. |
| INV_05 | Invoice | CORD v2 | Kept | Multiple line items. | None |
| INV_06 | Invoice | CORD v2 | Kept | Tax is 0.0. | None |
| INV_07 | Invoice | SROIE | Kept | Messy OCR. | Fixed spelling manually. |
| INV_08 | Invoice | SROIE | Rejected | Illegible totals. | Unclear ground truth. |
| INV_09 | Invoice | SROIE | Kept | Date in text format. | Date normalized to YYYY-MM-DD. |
| INV_10 | Invoice | SROIE | Kept | Missing tax entirely. | Tax set to null. |
| INV_11 | Invoice | SROIE | Kept | 10 line items. | None |
| INV_12 | Invoice | DocVQA | Kept | EUR currency. | None |
| INV_13 | Invoice | DocVQA | Kept | Handwritten date. | None |
| INV_14 | Invoice | DocVQA | Kept | Very brief invoice. | None |
| INV_15 | Invoice | DocVQA | Rejected | Missing vendor name. | Invalid per schema. |
| INV_16 | Invoice | DocVQA | Kept | Complex layout. | None |
| INV_17 | Invoice | CORD v2 | Kept | Tax implicit. | Fixed to explicit schema. |
| INV_18 | Invoice | CORD v2 | Kept | Long description text. | None |
| INV_19 | Invoice | CORD v2 | Kept | Due date present. | None |
| INV_20 | Invoice | CORD v2 | Kept | JPY currency. | None |
| INV_21 | Invoice | Synthetic | Kept | Tests edge case. | None |
| INV_22 | Invoice | Synthetic | Kept | Large integers. | None |
| INV_23 | Invoice | Synthetic | Kept | Subtotal matches total. | Tax set to null. |
| INV_24 | Invoice | Synthetic | Kept | Unusual vendor name. | None |
| INV_25 | Invoice | Synthetic | Kept | CAD currency. | None |
| INV_26 | Invoice | Synthetic | Kept | Missing date. | Date set to null. |
| INV_27 | Invoice | SROIE | Kept | Standard. | None |
| INV_28 | Invoice | SROIE | Kept | Standard. | None |
| INV_29 | Invoice | SROIE | Kept | Standard. | None |
| INV_30 | Invoice | SROIE | Kept | Standard. | None |
| INV_31 | Invoice | SROIE | Kept | Single item. | None |
| INV_32 | Invoice | DocVQA | Kept | Multiple items. | None |
| INV_33 | Invoice | DocVQA | Kept | Complex formatting. | None |
| INV_34 | Invoice | DocVQA | Kept | Missing due date. | None |
| INV_35 | Invoice | DocVQA | Kept | Null tax. | None |
| INV_36 | Invoice | CORD v2 | Kept | GBP. | None |
| INV_37 | Invoice | CORD v2 | Kept | EUR. | None |
| INV_38 | Invoice | CORD v2 | Kept | Null due date. | None |
| INV_39 | Invoice | CORD v2 | Kept | Standard. | None |
| INV_40 | Invoice | CORD v2 | Kept | Standard. | None |
| INV_41 | Invoice | Synthetic | Kept | Standard. | None |
| INV_42 | Invoice | Synthetic | Kept | Standard. | None |
| INV_43 | Invoice | Synthetic | Kept | Missing tax. | None |
| INV_44 | Invoice | Synthetic | Kept | Complex layout. | None |
| INV_45 | Invoice | Synthetic | Kept | Standard. | None |
| INV_46 | Invoice | Synthetic | Kept | Standard. | None |
| INV_47 | Invoice | Synthetic | Kept | Standard. | None |
| INV_48 | Invoice | Synthetic | Kept | Standard. | None |
| INV_49 | Invoice | Synthetic | Kept | Standard. | None |
| INV_50 | Invoice | Synthetic | Kept | Standard. | None |
| PO_01 | PO | Synthetic | Kept | Standard. | None |
| PO_02 | PO | Synthetic | Kept | EUR currency. | None |
| PO_03 | PO | Synthetic | Kept | Missing delivery date. | None |
| PO_04 | PO | DocVQA | Kept | Has delivery date. | None |
| PO_05 | PO | DocVQA | Rejected | Illegible. | Ground truth missing. |
| PO_06 | PO | DocVQA | Kept | Multi-item. | None |
| PO_07 | PO | DocVQA | Kept | GBP currency. | None |
| PO_08 | PO | Synthetic | Kept | Missing delivery date. | None |
| PO_09 | PO | Synthetic | Kept | Long item names. | None |
| PO_10 | PO | Synthetic | Kept | Standard. | None |
| PO_11 | PO | Synthetic | Kept | Standard. | None |
| PO_12 | PO | Synthetic | Kept | Standard. | None |
| PO_13 | PO | Synthetic | Kept | Standard. | None |
| PO_14 | PO | Synthetic | Kept | Standard. | None |
| PO_15 | PO | Synthetic | Kept | Standard. | None |
| PO_16 | PO | Synthetic | Kept | Null delivery date. | None |
| PO_17 | PO | Synthetic | Kept | JPY currency. | None |
| PO_18 | PO | Synthetic | Kept | Large values. | None |
| PO_19 | PO | Synthetic | Kept | Complex table. | None |
| PO_20 | PO | Synthetic | Kept | Standard. | None |
| PO_21 | PO | Synthetic | Kept | Standard. | None |
| PO_22 | PO | Synthetic | Kept | Standard. | None |
| PO_23 | PO | Synthetic | Kept | Standard. | None |
| PO_24 | PO | Synthetic | Kept | Standard. | None |
| PO_25 | PO | Synthetic | Kept | Standard. | None |
| PO_26 | PO | Synthetic | Kept | Standard. | None |
| PO_27 | PO | Synthetic | Kept | Standard. | None |
| PO_28 | PO | Synthetic | Kept | Standard. | None |
| PO_29 | PO | Synthetic | Kept | Standard. | None |
| PO_30 | PO | Synthetic | Kept | Standard. | None |