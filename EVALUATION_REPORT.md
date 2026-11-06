# Evaluation Report
## AI Document Intelligence System

### 1. Objective
Evaluate document extraction and processing across PDF, image,
Excel, and CSV files, including invalid and unsupported documents.

### 2. Test Environment
- Processing: Python
- PDF extraction: PyMuPDF
- OCR: Tesseract
- Spreadsheet processing: Pandas
- Database: SQLite
- Backend: FastAPI
- Frontend: Gradio

### 3. Multi-Format Evaluation Results

| Test File | Result | Time (seconds) | Extracted Characters | Fields Extracted |
|---|---|---:|---:|---:|
| sample_invoice_v2.pdf | Success | 0.4218 | 208 | 8 |
| sample_invalid_invoice.pdf | Success | 0.2470 | 141 | 8 |
| sample_spreadsheet_invoice.xlsx | Success | 3.7214 | 494 | 7 |
| sample_csv_invoice.csv | Success | 0.2742 | 251 | 7 |
| sample_xls_invoice.xls | Success | 0.2274 | 302 | 7 |
| sample_csv_invoice_v2.csv | Success | 0.1773 | 475 | 7 |
| history_test_invoice.png | Success | 2.3986 | 162 | 8 |
| multi_page_test.pdf | Success | 0.2019 | 135 | 0 |
| ocr_test.png | Success | 0.6238 | 139 | 6 |
| corrupted_test.pdf | Failed | 0.2290 | 0 | 0 |
| test_file.txt | Failed | 0.0000 | 0 | 0 |

### 4. Additional PDF Evaluation
A separate five-page PDF test was performed:
- Total pages: 5
- Processing time: 0.0239 seconds
- Extracted characters: 129
- Text extraction: Successful

### 5. Observations
- PDF, image, Excel, and CSV processing pipelines were exercised.
- OCR successfully extracted text from the tested images.
- The corrupted PDF was rejected with an extraction failure.
- Unsupported TXT input was rejected.
- Some invoices contained missing fields or arithmetic validation errors.
- The multi-page test PDF produced text but no invoice fields.

### 6. Limitations
- The evaluation used a small test set of 11 files.
- Extraction success does not guarantee correct invoice field extraction.
- No ground-truth dataset was used to calculate precision, recall,
  F1-score, or field-level accuracy.
- Invoice extraction is rule-based and may require manual correction.
- Line-item extraction is limited for some formats.

### 7. Conclusion
The system demonstrated document-processing functionality across
the tested formats and handled corrupted and unsupported inputs.
Further evaluation with a larger labelled dataset is required to
measure extraction accuracy and generalization.
