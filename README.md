# Assignment 2: Refining Requirements

## User (Functional) Requirements 
### Current Requirement 1: Separate Training Questions
_As a **developer**, I want the web scraper to parse each training entry and insert the question text into a dedicated Question field in the database to be able to review questions independently of answers_.

- **Assumptions**:
  - The raw data contains identifiable question text.
  - The parsing algorithm can reliably distinguish between questions and answers.
- **Validations**:
  - The system must correctly classify at least 95% of entries as questions or answers.
  - A validation report must log any entries that fail proper classification.

- **Actionable Tasks**:
  - Update the parsing algorithm to detect and extract question text.
  - Modify the database schema to include a dedicated Question column.
  - Implement unit tests to verify classification accuracy.

- **Outcome**:
  - Training questions and answers are stored separately, enabling developers to quickly review and utilize the question data for further analysis and model training.

### Current Requirement 2: Automated Bias Analysis and Reporting
_As a **developer**, I want the system to execute an automated bias analysis on the training data using predefined bias metrics to be able to verify that the data is balanced_.

- **Assumptions**:
  - Bias metrics and acceptable thresholds are defined and documented.
  - The training data includes measurable indicators relevant for bias detection.
- **Validations**:
  -The bias analysis module must produce a quantitative report that meets the predefined threshold criteria.
  - The system must flag any data subsets where bias exceeds acceptable limits.

- **Actionable Tasks**:
  - Integrate a bias detection algorithm into the data processing pipeline.
  - Develop a reporting module (or dashboard) that displays bias scores per category.
  - Create automated tests to ensure bias alerts trigger correctly when thresholds are breached.

- **Outcome**:
  - A comprehensive bias analysis report is generated automatically, enabling developers to identify and correct imbalances in the training data.

### Additional Requirement 3: Developer Dashboard for Data Quality
As a developer, I want the system to display a dashboard showing each training entry’s question, answer, classification status, and bias score to be able to verify data quality immediately.

- **Assumptions**:
  - Parsing and bias analysis modules output structured data.
- **Validations**:
  - The dashboard must support filtering by classification status and bias score.

- **Actionable Tasks**:
  - Develop a web interface that retrieves and displays the parsed data with filtering and search capabilities.
  - Integrate dashboard widgets for real-time data quality metrics.

- **Outcome**:
  - Developers can monitor data quality in real time, ensuring that issues in classification and bias are quickly identified and addressed.

### Additional Requirement 4: Configurable Bias Threshold Settings
_As a **developer**, I want the system to allow bias threshold values to be updated through a settings interface to be able to adjust parameters without code changes_.

- **Assumptions**:
  - Predefined bias metrics exist and may require periodic adjustment based on evolving project needs.
- **Validations**:
  - The settings interface must persistently store threshold updates and apply them in future bias analyses.

