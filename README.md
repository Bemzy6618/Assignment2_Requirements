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

