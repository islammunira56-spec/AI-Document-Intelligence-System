# Database Schema

The system uses SQLite for persistent storage.

## Application Tables

| Table | Purpose |
|---|---|
| documents | Uploaded document metadata and processing status |
| extracted_text | Text extracted from uploaded documents |
| invoices | Structured invoice information |
| line_items | Individual invoice items |
| processing_history | Document processing events |
| validation_errors | Invoice validation issues |
| correction_history | Manual correction records |

## Relationships

- documents.id → invoices.document_id
- documents.id → extracted_text.document_id
- documents.id → processing_history.document_id
- documents.id → validation_errors.document_id
- documents.id → correction_history.document_id
- invoices.id → line_items.invoice_id

## Database File

document_intelligence/documents.db

The database also contains sqlite_sequence, an internal SQLite table.
