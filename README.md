
# AI Document Intelligence System

## Overview
An AI-assisted document processing system designed to upload, extract,
validate, search, and manage invoice information from multiple file formats.

## Supported Formats
- PDF
- JPG / JPEG
- PNG
- TIFF
- XLSX
- XLS
- CSV

## Main Features
- Text extraction from digital PDFs
- OCR for scanned PDFs and images
- Spreadsheet and CSV processing
- Structured invoice data extraction
- Invoice validation and arithmetic checks
- Duplicate invoice detection
- Manual invoice correction and revalidation
- Document processing history
- Keyword-based invoice search
- REST API using FastAPI
- Web interface using Gradio
- SQLite database storage

## Technologies
- Python
- FastAPI
- Gradio
- SQLite
- Pandas
- PyMuPDF
- Tesseract OCR
- Pillow
- Requests

## Project Structure
AI_Document_Intelligence_System/
- document_intelligence/
  - uploads/
  - logs/
  - documents.db
- tests/
  - test_document_processing.py
- README.md

## Running the System
Run the project notebook in Google Colab.
Mount Google Drive, install the dependencies, connect the database,
define the processing functions, and start the FastAPI and Gradio services.

## API Endpoints
- GET / : API health check
- POST /upload : Upload a document
- GET /documents : List documents
- GET /invoices : List extracted invoices
- GET /documents/{document_id}/status : Processing status
- GET /search?q= : Search invoices
- PUT /invoices/{invoice_id}/correct : Correct invoice fields
- POST /retry/{document_id} : Retry document processing

## Testing
Eight automated smoke checks passed:
- PDF processing
- Excel processing
- CSV processing
- Image OCR
- Corrupted PDF handling
- Unsupported file handling
- API health
- Keyword search

Results are stored in:
document_intelligence/logs/automated_test_results.json

## Current Limitations
- Invoice extraction is rule-based and may require manual review.
- Line-item extraction is limited for some document formats.
- Search currently uses keyword matching rather than embedding-based semantic search.
- Extraction success does not guarantee that every invoice field is accurate.
