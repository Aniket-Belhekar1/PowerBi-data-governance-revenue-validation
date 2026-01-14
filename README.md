# Power BI Data Governance – Revenue Validation Framework

## Overview
This project demonstrates how data governance principles can be applied in Power BI to prevent, detect, and explain revenue reporting inconsistencies across dashboards.

Instead of focusing on visualization, the project focuses on:
- Metric definition and certification
- Controlled data modeling
- Governance validation and root-cause analysis
- Prevention of metric drift

---

## Problem Statement
In many organizations, different dashboards report different revenue numbers due to:
- Multiple revenue definitions
- Use of raw transactional fields
- Inconsistent filtering logic
- Lack of certified metrics

This project answers a common enterprise question:
**“Why do two dashboards show different revenue figures, and how can this be prevented?”**

---

## Key Governance Decisions

### Certified Revenue Definition
- Revenue = Net revenue from completed orders only
- Formula: `Sales – (Sales × Discount)`
- Cancelled and returned orders are excluded
- Grain: Order line
- Status: Certified

All business dashboards use certified measures only.

---

## Architecture

### Data Layers
- **Raw Layer**: Preserves source-system reality (duplicates, inconsistent formats)
- **Certified Layer**: Enforces approved business rules and definitions
- **Semantic Layer**: Exposes only certified measures for reporting

### Model Design
- Star schema
- Single-direction relationships
- No implicit measures
- Certified measures prefixed with `CM_`

---

## Governance Validation Framework
A dedicated governance validation dashboard compares:
- Raw revenue (unguarded aggregation)
- Certified revenue (approved logic)

The dashboard:
- Quantifies revenue overstatement
- Highlights category-level root causes
- Shows time-based metric drift
- Flags mismatches automatically

This page is used for governance validation only, not business reporting.

---

## Outcomes
- Identified ~22% revenue overstatement caused by ungoverned logic
- Explained variance by category and month
- Prevented recurrence through certified metrics and controlled modeling

---

## Tools Used
- Power BI Desktop
- Power Query
- DAX
- GitHub for documentation and versioning
