# AI Prompts and Development Disclosure

## AI Development Disclosure

AI assistance (ChatGPT) was used during the development of this AI Document Intelligence System.

The assistance included:
- Designing and implementing document-processing workflows.
- Developing PDF, image, Excel, and CSV extraction functionality.
- Building invoice extraction, validation, and duplicate-detection logic.
- Developing FastAPI endpoints and the Gradio frontend.
- Debugging errors involving API routes, database operations, and application integration.
- Preparing test cases and project documentation.

All generated code and suggestions were reviewed, adapted, and tested during implementation. The developer remained responsible for integrating the components, running the application, evaluating its behavior, and documenting its limitations.

## Representative AI Prompts Used

The following are representative summaries of prompts used during development, not a verbatim transcript of every interaction.

1. Implement a document-processing pipeline supporting PDF, JPG, PNG, TIFF, XLSX, XLS, and CSV files.
2. Extract text from digital and scanned PDF documents using appropriate extraction and OCR methods.
3. Extract invoice fields such as invoice number, date, supplier, customer, subtotal, tax, total, and currency.
4. Implement invoice validation, duplicate detection, and correction with revalidation.
5. Develop FastAPI endpoints for uploading, retrieving, searching, and correcting invoice records.
6. Build a Gradio interface for document upload, invoice review, search, and correction.
7. Debug application errors and verify API and database integration.
8. Create automated smoke tests and an evaluation report for supported file formats.

## Testing and Limitations

The application was tested using multiple document formats and automated smoke checks. Eight smoke checks passed during the recorded test run.

The system uses rule-based invoice field extraction rather than a trained invoice-understanding model. Extraction quality can vary depending on document layout, image quality, and text formatting. Further work is needed to improve field-level accuracy, line-item extraction, and evaluation against manually verified ground truth.
