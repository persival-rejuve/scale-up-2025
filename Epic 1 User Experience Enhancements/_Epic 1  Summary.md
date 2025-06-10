# Epic 1: User Experience Enhancements - Summary

## 1. Macro Roadmap Overview

| Seq | Initiative                                    | Why first/when                                                                       | Key Teams                        | High-level outputs                                           |
| --- | --------------------------------------------- | ------------------------------------------------------------------------------------ | -------------------------------- | ------------------------------------------------------------ |
| 1   | **PDF clinical-exam ingestion**               | Highest user benefit vs. code risk; unlocks richer data for BayesNet & scoring       | BE, Data Eng/Sci, ML, UX, DevOps | Upload UX, OCR/NER service, mapping layer, review UI         |
| 1.1 | **OCR options for clinical-exam ingestion**   | Enhancement to PDF ingestion for better data extraction                              | ML, LLLM, Data Eng/Sci, BE       | ML models, OCR improvements, LLM, extraction accuracy        |
| 2   | **Export Data**                               | Essential feature for data portability and medical sharing                           | BE, FE, UX, DevOps               | Export formats (CSV/PDF), secure delivery, visualization     |
| 3   | **Meal and Ingredient using Computer Vision** | Visual input for nutrition tracking enhancing user experience                        | ML, UX, FE, BE                   | Image recognition, food database, nutritional analysis       |
| 3.1 | **Computer Vision Technical Research**        | Technical evaluation of CV APIs and tools for meal recognition                       | ML, Data Eng/Sci                 | API comparisons, performance metrics, integration options    |
| 4   | **Multilanguage framework**                   | Required for global scale; minimal cross-team coupling once translation infra is set | FE/UX, BE, DevOps                | i18n wrapper, string files, RTL/LTR support, translation CMS |
| 5   | **Gamification layer**                        | Builds retention; depends on i18n so copy is localized                               | UX, FE, BE, Data                 | Points/levels DB tables, rewards service, UI badges          |
| 6   | **Chat with my data**                         | Enhanced user experience through conversational interface with personal data         | ML, BE, FE, UX                   | Chat interface, data retrieval, NLP processing               |
| 7   | **Figma to APP Prototypes**                   | Internal speed boost; runs parallel because it doesn't ship to prod users directly   | UX, FE, ML                       | AI agent, code-gen scripts, demo pipeline                    |
| 7.1 | **Figma to APP Technical Research**           | Evaluation of AI tools for rapid Figma-to-Flutter conversion                         | UX, FE, ML                       | Tool comparisons, workflow options, integration methods      |
| 8   | **Talk to the APP**                           | Voice interface enhancement for accessibility and convenience                        | ML, FE, UX                       | Speech recognition, voice commands, audio feedback           |

> _This roadmap provides a sequential view of our development priorities, with each initiative building upon capabilities established in previous ones._

---

## 2. Story Summaries

### Story 1: PDF Clinical-Exam Ingestion

**Product Outcome:** A user can upload lab-report PDFs, and the app automatically extracts test results, matches them to our internal variable catalog, stores them, and shows a review/confirmation screen before saving.

**Key Phases:**
1. **PDF Upload & Storage** - Secure file upload with validation and progress indicators
2. **OCR & Text Extraction** - Convert documents to structured data using OCRmyPDF and Ollama LLM
3. **User Review & Confirmation** - Present extracted data for verification before saving

**Architectural Components:**
- **Storage:** Raw PDFs in S3 with user-scoped prefixes
- **Parsing:** OCRmyPDF based on Tesseract for document processing
- **Data Extraction:** Ollama-hosted LLM for clinical term recognition
- **Mapping:** Dictionary + fuzzy matcher for standardization
- **Validation:** Unit conversion rules and clinical range checks

**Key Risks & Mitigations:**
- **Low-quality scans:** Enforce minimum DPI, provide scanning guidance
- **New lab analyte codes:** Self-service alias entry by Clinical Admin
- **Regulatory compliance:** HIPAA BAA with cloud provider, data minimization

---

### Story 2: Export Data

**Product Outcome:** Users can export their health data in various formats (.csv, PDF) for sharing with healthcare providers, importing into other systems, or keeping personal records.

**Implementation Approach:**
- **Phase 1:** Basic CSV Export with email delivery (2-3 weeks)
- **Phase 2:** Enhanced PDF Reports with visualizations and LLM-generated insights (4-6 weeks)

**Key Features:**
- Data category selection with granular privacy controls
- Multiple format options (CSV, PDF) with consistent formatting
- Secure delivery via email with encryption
- Data visualization and trend analysis in PDF reports

**Architectural Components:**
- Backend API endpoints for export requests
- Lambda service for data processing and format generation
- Email delivery service with secure attachments
- LLM integration for data insights and narrative generation

**Key Risks & Mitigations:**
- **Data privacy:** End-to-end encryption and access controls
- **Large exports:** Async processing with email notification
- **Medical terminology:** Consistent labeling across formats

---

### Story 3: Meal and Ingredient using Computer Vision

**Product Outcome:** Users can take photos of meals with their phone camera, and the app will identify the meal, its ingredients, and provide nutritional information for health tracking.

**Implementation Approach:**
- Hybrid solution combining LogMeal Food AI and Spoonacular Food API

**Key Phases:**
1. **Image Capture & Upload** - Streamlined photo taking with guidance
2. **Multi-API Recognition** - Food identification with ingredient breakdown
3. **LLM Enhancement** - Nutritional enrichment and portion estimation
4. **User Confirmation** - Review and adjust identified items and portions

**Reusable Services:**
- Secure Image Storage Service
- Ollama-hosted LLM Service for contextual processing
- Lambda Data Processing Service for standardization

**Key Risks & Mitigations:**
- **Recognition accuracy:** Hybrid API approach with manual override
- **Cultural food diversity:** Continuous model training with regional examples
- **Privacy concerns:** Local image processing where possible

---

### Story 4: Multilanguage Support

**Product Outcome:** Global users can choose their preferred language during registration and use the app entirely in that language, with all UI elements, educational content, and imported data in a familiar, localized form.

**Key Phases:**
1. **Core UI Localization** - Language selector and string bundle implementation
2. **Academic Paper & Hallmark Translation** - Translated educational content with LLM fallback
3. **External Data & Unit Conversion** - Cross-language term mapping and locale-specific units

**Architectural Components:**
- String bundles stored as key-value pairs in high-performance data store
- Ollama-hosted LLM for on-demand translation and term mapping
- Unit conversion service for locale-specific measurements
- Translation caching and asynchronous processing

**Key Risks & Mitigations:**
- **Accurate medical term mapping:** Clinical terminology library with manual overrides
- **LLM translation costs:** Aggressive caching and pre-translation of common content
- **Review capacity:** Scheduled review slots and medical intern crowd-sourcing

---

### Story 5: Gamification Layer

**Product Outcome:** Users engage more deeply with the app through achievement systems, progress tracking, and rewards that motivate consistent health monitoring and positive behaviors.

**Key Features:**
- Achievement system with badges for health milestones
- Daily streaks and challenges to encourage regular use
- Progress visualization for long-term health goals
- Social sharing options with privacy controls

**Architectural Components:**
- Achievement rules engine with configurable parameters
- User progress tracking in dedicated database tables
- Notification system for milestone alerts
- Privacy-focused social sharing mechanisms

**Key Risks & Mitigations:**
- **Overjustification effect:** Balance rewards with intrinsic motivation
- **Social sharing misuse:** Clear guidelines and user reporting mechanisms
- **Data privacy:** Ensure secure storage and access controls for user progress

---

### Story 6: Chat with My Data

**Product Outcome:** Users can interact with their health data through natural language conversations, easily understanding patterns and getting insights without navigating complex interfaces.

**Implementation Approach:**
- Web-based chat interface accessible via in-app webview and standard browsers
- Future transition to fully native implementation based on user feedback

**Key Features:**
1. **Natural Language Query Processing** - Conversational interface for data questions
2. **Health Insights & Pattern Recognition** - AI-driven analysis of personal health data
3. **Suggested Interactions** - Context-aware question recommendations

**Reusable Services:**
- Ollama-hosted LLM Service for conversation handling
- VectorDB/GraphDB Integration for semantic health data searches
- Lambda Data Processing Service for structured data retrieval

**Key Risks & Mitigations:**
- **Data privacy:** Local processing of sensitive information
- **Medical accuracy:** Clear source attribution and confidence levels
- **User trust:** Transparent AI limitations and human review options

---

### Story 7: Figma to APP Prototypes

**Product Outcome:** Development teams can rapidly convert Figma designs to functional Flutter prototypes using AI-assisted code generation, accelerating the development process.

**Key Goals:**
- Reduce design-to-prototype time by 60%
- Ensure consistent implementation of design specifications
- Enable designers to preview functional implementations earlier
- Accelerate feedback loops between design and development

**Implementation Components:**
- AI agent for design pattern recognition and code generation
- Flutter widget templates and component library
- Integration pipeline between Figma and development environment
- Visual regression testing system

**Key Risks & Mitigations:**
- **Code quality:** Manual review and established style guide enforcement
- **Edge case handling:** Hybrid approach with AI suggestions and developer refinement
- **Learning curve:** Comprehensive training and documentation

---

### Story 7.1: Figma to APP Technical Research

**Product Outcome:** A comprehensive evaluation of available AI tools and methodologies for automated Figma-to-Flutter conversion to inform the implementation strategy.

**Research Focus Areas:**
- AI model comparison for design recognition accuracy
- Integration options between design tools and code repositories
- Workflow optimization for designer-developer collaboration
- Performance benchmarks for various complexity levels

**Deliverables:**
- Comparative analysis of available tools and APIs
- Prototype workflow demonstration with selected tools
- Implementation roadmap and resource requirements
- ROI projection and success metrics framework

---

### Story 8: Talk to the APP

**Product Outcome:** Users can interact with the app through voice commands and receive audio responses, enhancing accessibility and allowing hands-free operation in various contexts.

**Key Features:**
1. **Voice Command Processing** - Recognition and execution of spoken instructions
2. **Audio Response System** - Natural language feedback through speech synthesis
3. **Conversational Context Maintenance** - Continuity across voice interactions
4. **Multimodal Integration** - Seamless transition between voice and touch interfaces

**Architectural Components:**
- Voice recognition service with offline capabilities
- Text-to-speech engine with natural voice qualities
- Context management system for conversation history
- Intent classification model for action mapping

**Key Risks & Mitigations:**
- **Accuracy in noisy environments:** Advanced noise filtering and confirmation prompts
- **Accent and dialect handling:** Diverse training data and continuous improvement
- **Privacy concerns:** On-device processing for sensitive commands and opt-in policies

---
