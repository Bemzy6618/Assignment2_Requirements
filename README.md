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

- **Actionable Tasks**:
  - Create a configuration module with an input form for bias thresholds.
  - Modify the bias analysis module to read and apply these settings dynamically.

- **Outcome**:
  - Developers can update bias thresholds easily, ensuring the bias analysis remains relevant and aligned with current project requirements.

### Additional Requirement 5: Automated Bias Alert Notifications
_As a **developer**, I want the system to send automated notifications when bias scores exceed set thresholds to be able to address data quality issues immediately_.

- **Assumptions**:
  - A notification service (e.g., email or messaging) is available.
- **Validations**:
  - Alerts must trigger in at least 95% of cases where bias scores exceed acceptable limits.

- **Actionable Tasks**:
  - Integrate a notification module that monitors bias analysis results and sends alerts.
  - Configure threshold-based triggers for bias alerts.

- **Outcome**:
  - Developers receive timely alerts about data imbalances, allowing for prompt corrective actions to maintain data quality.

## System (Non-Functional) Requirements
### Requirement 1: Audit Logging for Data Processing
_As a **system administrator**, I want to record audit logs for each data processing step (web scraping, parsing, bias analysis) to be able to track the workflow_.

- **Assumptions**:
  - Each processing step can emit identifiable log events.
- **Validations**:
  - Logs must include timestamps, processing status, and error messages with a retention period of 30 days.

- **Actionable Tasks**:
  - Implement logging in each module.
  - Centralize logs in a queryable store.

- **Outcome**:
  - Comprehensive audit logs provide traceability and ensuring that data processing issues can be quickly identified and resolved.

### Requirement 2: Performance Monitoring of the Pipeline
_As a **system administrator**, I want to measure processing times for each batch of training data to be able to ensure that the pipeline meets performance benchmarks_.

- **Assumptions**:
  - Processing time metrics are measurable accurately.
- **Validations**:
  - The system must process at least 1,000 training entries in under 60 seconds.

- **Actionable Tasks**:
  - Insert performance monitoring hooks in the data processing pipeline.
  - Generate periodic performance reports accessible via the dashboard.

- **Outcome**:
  - The system consistently meets performance benchmarks, ensuring efficient processing of training data and a smooth workflow.

### Requirement 3: Secure Access Control
_As a **system administrator**, I want to enforce role-based access control on the dashboard and configuration settings to be able to protect sensitive training data and parameters_.

- **Assumptions**:
  - An authentication mechanism exists for developers and authorized personnel.
- **Validations**:
  - Only authorized users must access the dashboard and settings; unauthorized attempts must be denied and logged.

- **Actionable Tasks**:
  - Implement an authentication module with role-based permissions.
  - Conduct regular security audits of access logs.

