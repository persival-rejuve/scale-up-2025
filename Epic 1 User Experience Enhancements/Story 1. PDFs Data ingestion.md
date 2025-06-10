### Epic: **User Experience Enhancements — PDF Data Ingestion**

---

#### Story Title

**Enable PDF Clinical Data Ingestion into Longevity App**

*Version: 0.1 | Date: 2025-06-07 | Created by: Persival Ballesté*

---

#### Story Overview

As a **global user** of the Longevity App,  
I **want to upload a PDF file with my clinical data into the APP and see the data in the UI**,  
so that I can store all my clinical data into the APP quickly and don't need to manually type all the data.

---

#### Functional Scope

| Phase                             | Capability                                                                                                                                                                                                       | Summary                                                   |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **1. PDF Upload & Storage**       | • Add **file upload** UI component to clinical data section. • Create secure storage for PDFs in **`user/{id}/clinical-docs/`** path. • Implement progress indicators and validation (file type, max size 10MB). | Enables users to securely submit their clinical documents |
| **2. OCR & Text Extraction**      | • Implement OCRmyPDF service to convert image-based PDFs to text. • Extract structured data using an Ollama-hosted LLM. • Create mapping layer to translate extracted terms to database variables and perform unit conversions.  | Converts unstructured document data to structured format  |
| **3. User Review & Confirmation** | • Present extracted data to user in editable format. • Allow users to correct/confirm extracted values before saving. • Store both raw PDF and structured data with versioning.                                  | Ensures data accuracy with human verification             |

#### Process Flow Visualization

```mermaid
graph TB
    subgraph "Phase 1: PDF Upload & Storage"
        A1[User selects clinical PDF document] --> A2[Upload validation: type & size]
        A2 --> A3[Secure transfer with encryption]
        A3 --> A4[Store in user-specific secure path]
    end
    
    subgraph "Phase 2: OCR & Text Extraction"
        B1[OCRmyPDF processes document] --> B2[Extract raw text from PDF]
        B2 --> B3[Ollama-hosted LLM analysis]
        B3 --> B4[Clinical term identification]
        B4 --> B5[Unit standardization & conversion]
        B5 --> B6[Generate structured JSON]
    end
    
    subgraph "Phase 3: User Review & Confirmation"
        C1[Present extracted data to user] --> C2[Allow edits & corrections]
        C2 --> C3[Validation against reference ranges]
        C3 --> C4[User confirmation]
        C4 --> C5[Store in RejuveDB]
        C5 --> C6[Version control & audit trail]
    end
    
    A4 --> B1
    B6 --> C1
    
    style A1 fill:#ffdd99,stroke:#ff9900
    style B3 fill:#99ccff,stroke:#3366ff
    style C4 fill:#99ff99,stroke:#33cc33
```

**Chart Explanation:**

This workflow illustrates the three key phases of clinical data ingestion:

1. **Upload Phase**: The user selects and uploads their clinical PDF document, which undergoes validation before secure storage.

2. **Extraction Phase**: OCRmyPDF processes the document to extract raw text, which is then analyzed by the Ollama-hosted LLM. The LLM identifies clinical terms, standardizes units, and generates structured JSON output.

3. **Review Phase**: The extracted data is presented to the user for review and possible correction. After validation and confirmation, the data is stored in RejuveDB with proper versioning and audit trail.

#### System Sequence Diagram

```mermaid
sequenceDiagram
    participant User
    participant MobileApp
    participant API
    participant Storage
    participant OCR as OCRmyPDF Service
    participant LLM as Ollama LLM
    participant RejuveDB

    User->>MobileApp: Select clinical PDF
    MobileApp->>MobileApp: Validate file (type & size)
    MobileApp->>API: Upload PDF with progress indicator
    API->>Storage: Store encrypted PDF
    Storage-->>API: Confirm storage
    API-->>MobileApp: Upload successful
    
    API->>OCR: Trigger OCR processing
    OCR->>Storage: Retrieve PDF
    Storage-->>OCR: Return PDF content
    OCR->>OCR: Extract text from PDF
    OCR-->>LLM: Send extracted text
    
    LLM->>LLM: Identify clinical terms
    LLM->>LLM: Translate (if needed)
    LLM->>LLM: Standardize units
    LLM-->>API: Return structured JSON
    
    API-->>MobileApp: Send extracted data
    MobileApp->>User: Display data for review
    
    User->>MobileApp: Review and edit if needed
    User->>MobileApp: Confirm data
    MobileApp->>API: Submit confirmed data
    API->>RejuveDB: Store structured data
    RejuveDB-->>API: Confirm storage
    API-->>MobileApp: Confirmation complete
    MobileApp-->>User: Show success message
```

**Sequence Diagram Explanation:**

This sequence diagram illustrates the temporal flow and interactions between system components:

1. **User Interaction**: The process begins with the user selecting and uploading a clinical PDF document through the mobile app interface.

2. **Processing Pipeline**: After validation and secure storage, the document flows through the OCRmyPDF service for text extraction, then to the Ollama LLM for intelligent analysis.

3. **Data Review**: The extracted clinical data is presented back to the user for review and confirmation before final storage in RejuveDB.

4. **Service Communication**: The diagram highlights how different services communicate with each other, showing the complete data flow from upload to final storage.

---

#### Acceptance Criteria

1. **PDF Upload**
    - Given a user with clinical data PDF, when they access the upload section, they can select and upload a PDF up to 10MB in size.
        
2. **Extraction Accuracy**
    - System correctly extracts at least 90% of standard lab values (glucose, cholesterol, etc.) from commonly formatted lab PDFs.
        
3. **Data Validation**
    - Extracted values are validated against expected ranges and units, with flagging of potential errors.
        
4. **User Review Flow**
    - After upload, user is presented with extracted data for review, can edit incorrect values, and must confirm before data is saved to their profile.
        
5. **Performance**
    - PDF processing completes in ≤ 15 seconds for standard 5-page documents, with progress indicators shown to user.
        
---

#### Implementation Tasks (high-level)

- **Front-End (Flutter)**
    - Create PDF upload component with progress indicator.
    - Develop data review/edit interface with confirmation flow.
    - Implement unit display based on user preferences.
        
- **Back-End / API**
    - Create `/upload-clinical-pdf` endpoint with S3 presigned URLs.
    - Develop extraction service with OCRmyPDF and Ollama LLM pipeline.
    - Build mapping service to convert extracted terms to database fields.
    - Implement lambda service to process JSON output for RejuveDB storage.
        
- **Database & Storage**
    - Table: `user_clinical_docs` (user_id, doc_id, upload_date, status, file_path).
    - Table: `extracted_clinical_data` (doc_id, variable_name, value, unit, confidence, reviewed).
    - Add versioning for data corrections and historical records.
        
- **Machine Learning & LLM Integration**
    - Configure Ollama-based LLM for clinical document interpretation.
    - Implement text processing for multiple languages and unit conversions.
    - Train the LLM to output structured JSON for database ingestion.
    - Create feedback loop for extraction improvements.
        
- **DevOps**
    - Set up secure S3 bucket with appropriate access policies.
    - Configure extraction service scaling based on queue depth.
    - Monitor processing times and extraction accuracy metrics.
        

---

#### Dependencies & Risks

|Item|Impact|Mitigation|
|---|---|---|
|Variable quality of PDF documents|High|Implement image preprocessing and provide guidance on scan quality|
|Diverse clinical lab formats|High|Train on diverse document corpus and implement format detection|
|PHI/HIPAA compliance|Critical|Process all documents in HIPAA-compliant environment with encryption|
|Performance at scale|Medium|Implement queue system with auto-scaling extraction workers|

---

#### Non-Functional Requirements

- **Security**: All PDFs must be encrypted at rest and in transit; processing must occur in HIPAA-compliant environment.
- **Scalability**: System should handle concurrent uploads during peak periods with minimal latency increase.
- **Accessibility**: Provide alternative manual data entry for users who cannot upload PDFs.
- **Privacy**: Implement document retention policies and user-controlled data deletion.

---

#### Definition of Done

- All acceptance criteria met on staging environment and validated with test PDFs from different labs.
- Processing accuracy metrics reach ≥90% for common labs, ≥75% for specialized tests.
- Regression tests ensure upload and extraction flows remain functional across app updates.
- User testing confirms intuitive navigation through upload → review → confirmation flow.
- Feature flag toggled **ON** in production after processing 1000+ documents with ≥85% user satisfaction.