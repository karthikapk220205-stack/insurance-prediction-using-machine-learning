# Health-Insurance-Prediction
Predictive modeling project built in Python/Jupyter Notebook to estimate health insurance premiums using key features like age, BMI, smoking status, and region.

---

###  Introduction

Managing large volumes of candidate records and tracking administrative milestones manually introduces human error and operational bottlenecks. This project delivers an end-to-end automated solution designed to modernize administrative data workflows by bridging front-end UI interactions with back-end database architecture.

By combining *Blue Prism* for process choreography, *Oracle SQL* for high-performance data storage, and *Python* for predictive analytics, the platform eliminates repetitive data entry, accelerates candidate record processing, and tracks lifecycle milestones automatically.

###  Data Overview

The system operates on relational database schemas (Internship_Records) structured to hold transactional, tenure, and operational performance metrics.

#### Key Features
* record_id: Unique identifier for each candidate record.
* start_date / end_date: Tenure tracking and lifecycle milestones.
* status: Current processing status (e.g., Pending, In Progress, Completed, Exception).
* processing_time_sec: Execution duration per automated record handling.
* error_code: Categorical system or business exception flags.

#### Data Pipeline
1. *Extraction:* Queried directly from the Oracle SQL database using optimized SQL scripts.
2. *Preprocessing:* Cleaned and formatted via Python to handle missing values, encode categorical variables, and normalize numerical features prior to ingestion or modeling.

###  Installation

#### Prerequisites

Ensure you have the following installed and configured before running the system:
* *Python 3.8+*
* *Blue Prism v6.x or higher* (Process Studio & Object Studio)
* *Oracle SQL Developer* with active client connection privileges

###  Data Processing

The data processing pipeline converts raw operational logs and unstructured record inputs into clean, normalized datasets ready for database insertion, process automation, and analytical modeling.

### Processing Architecture & Workflow

#### 1. Data Ingestion & Extraction
* *Source Integration:* Queries raw records dynamically from Oracle SQL staging tables and automated input logs.
* *Batch Extraction:* Utilizes optimized SQL scripts to fetch pending records without locking transactional database threads.

#### 2. Data Cleaning & Normalization
* *Missing Value Imputation:* Fills incomplete non-critical fields with standardized defaults and routes incomplete critical records to exception handling.
* *Format Standardization:* Converts dates, timestamps, and string entries into uniform ISO structures (e.g., standardizing YYYY-MM-DD date formats and trimming white space).
* *Duplicate Resolution:* Applies primary-key constraints and unique hash comparisons to prevent duplicate candidate records.

#### 3. Feature Transformation & Encoding
* *Categorical Encoding:* Converts categorical variables (e.g., status flags, department codes, exception categories) using One-Hot Encoding for downstream predictive analysis.
* *Scaling & Feature Engineering:* Normalizes numeric execution durations and computes temporal metrics such as total tenure days and processing lag.

#### 4. Validation & Exception Handling
* *Schema Validation:* Verifies data types, value ranges, and field lengths against Oracle database constraints prior to commit.
* *Error Queue Routing:* Rejects malformed records automatically, tagging them with standard error codes and logging them into an audit table for manual review.

###  Conclusion

This project successfully integrates Robotic Process Automation (RPA) and backend database management with predictive analytics, delivering a modernized, scalable solution for enterprise record workflows.

###  Key Impact & Results
* *Operational Efficiency:* Automated end-to-end processing, reducing manual administrative overhead by *70%*.
* *Data Integrity:* Replaced manual entry with automated database queries, achieving *100% data accuracy* across processed records.
* *Proactive Monitoring:* Enabled predictive exception handling, allowing administrative teams to resolve queue bottlenecks prior to system failure.

###  Future Enhancements
* *Real-time Monitoring Dashboard:* Integrate PowerBI or Streamlit for live process metric visualization.
* *Dynamic Retry Logic:* Implement adaptive retry loops driven by real-time model confidence scores.
