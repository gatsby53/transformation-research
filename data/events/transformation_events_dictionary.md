# transformation_events.csv Data Dictionary

## Purpose

Store important company events that may contribute to business transformation and enable cross-company event analysis.

---

# Table Definition

| Column      | Type    | Required | Description                                              |
| ----------- | ------- | -------- | -------------------------------------------------------- |
| event_id    | string  | Yes      | Unique identifier of the event. Format: COMPANY_YEAR_SEQ |
| company     | string  | Yes      | Company name. Must match the company master.             |
| event_date  | date    | No       | Date of the event in YYYY-MM-DD format.                  |
| event_year  | integer | Yes      | Event year used for time-series analysis.                |
| event_type  | string  | Yes      | Event classification defined in event_type_master.csv.   |
| title       | string  | Yes      | Short event title.                                       |
| description | string  | No       | Detailed description of the event.                       |
| source_id   | string  | No       | Identifier linked to source_index.csv.                   |
| confidence  | string  | Yes      | Reliability of the record (High / Medium / Low).         |
| notes       | string  | No       | Additional notes, assumptions, or estimation methods.    |

---

# Column Definitions

## event_id

Unique key.

Examples:

* MSFT_2008_001
* AMZN_2006_001
* NVDA_2016_001

---

## confidence

### High

Directly confirmed from primary sources.

### Medium

Derived from company disclosures or secondary sources with reasonable certainty.

### Low

Estimated or inferred with limited evidence.

---

# Data Principles

* Primary sources are preferred.
* Estimated values are allowed if the estimation method is documented.
* Missing values are permitted.
* Facts and hypotheses must be separated.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| v1.0    | 2026-06-30 | Initial version |
