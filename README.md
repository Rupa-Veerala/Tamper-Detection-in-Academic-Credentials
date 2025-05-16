#  Tamper Detection in Academic Credentials



---

##  Objective

To build a rule-based prototype that detects tampering in academic credentials, specifically:

- Degree Certificates  
- Academic Transcripts  
- Professional Certifications  

The system flags inconsistencies in metadata, template usage, and document editors across structured Excel files and embedded PDF metadata.

---

##  Methodology

###  1. Data Loading
- Loaded structured data from Excel sheets for each document type:
  - Degree_Certificates  
  - Academic_transcripts  
  - professionals_Certification  

###  2. Metadata Verification (PDF)
- Parsed metadata fields from generated PDFs using `PyPDF2`:
  - `/CreationDate`, `/ModDate`, `/Author`, `/Title`
- Flagged PDFs if:
  - Modification date > issue date  
  - Editor is not in the approved list  
  - Template title is not recognized  

###  3. Tamper Detection Logic
- For Excel files:
  - Invalid template names  
  - Fake or unrecognized certification levels  
  - Unauthorized editors  
  - Timestamps inconsistent with issue dates  

- For PDFs:
  - Metadata mismatches  
  - Unauthorized modifications  

###  4. Output Generation
- Flagged data exported as:
  - `flagged_documents.xlsx` – Excel-based tampering flags  
  - `tampered_pdf_report.xlsx` – PDF-based tampering flags  
- Created synthetic PDFs under:
  - `generated_pdfs/` – With embedded metadata for simulation
  - sample generated pdf output: ![image](https://github.com/user-attachments/assets/e83edb5b-7fd1-4f94-a837-155ed2faf5ba)
  - sample flagged xsxl sheet output: ![image](https://github.com/user-attachments/assets/e3142aa2-23ac-4822-8e91-b9d7e1a4a430)
  - sample tampered_pdf: ![image](https://github.com/user-attachments/assets/c3b51cc0-64c9-4f31-900e-988dc70b03ca)

---

##  Conclusion

This project demonstrates a metadata-driven tamper detection system for academic credentials using structured Excel data and PDF metadata parsing. It provides a foundational framework that can be extended to include advanced verification features like digital seals, OCR analysis, and API integrations for real-world deployment.

---
