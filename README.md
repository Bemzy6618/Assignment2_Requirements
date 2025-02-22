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


