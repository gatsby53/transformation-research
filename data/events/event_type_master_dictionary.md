# event_type_master.csv Data Dictionary

## Purpose

Define standardized event classifications used in transformation_events.csv.

---

# Table Definition

| Column                  | Type    | Description                                                                           |
| ----------------------- | ------- | ------------------------------------------------------------------------------------- |
| event_type              | string  | Unique event type code                                                                |
| category                | string  | Higher-level event category                                                           |
| description             | string  | Detailed explanation of the event type                                                |
| is_transformation_event | integer | 1 if the event is considered directly related to business transformation, otherwise 0 |

---

# Event Type Definitions

| event_type     | Description                                     |
| -------------- | ----------------------------------------------- |
| FIRST_SUCCESS  | Core business achieved dominant market position |
| NEW_BUSINESS   | Launch of a new business initiative             |
| SECOND_PILLAR  | New business became a major earnings pillar     |
| THIRD_PILLAR   | Third business pillar emerged                   |
| MANAGEMENT     | CEO appointment or major management change      |
| ORGANIZATION   | Major organizational restructuring              |
| ACQUISITION    | Acquisition of another company or business      |
| DIVESTITURE    | Sale or spin-off of a business                  |
| PRODUCT_LAUNCH | Launch of a major product or service            |
| TECHNOLOGY     | Major technological breakthrough                |
| CAPEX          | Large capital investment                        |
| PARTNERSHIP    | Strategic alliance or partnership               |
| REGULATION     | Regulatory or legal event                       |
| CRISIS         | Major crisis or disruption                      |
| OTHER          | Other significant event                         |

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| v1.0    | 2026-06-30 | Initial version |
