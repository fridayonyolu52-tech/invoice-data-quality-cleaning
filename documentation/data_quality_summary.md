# Data Quality Summary

## Project

**Invoice Data Quality & Cleaning**

## Project Type

Data Cleaning & Quality Assurance

## Dataset

Invoice Transaction Dataset

## Dataset Size

500 invoice records

## Tool

Microsoft Excel

## Objective

Identify, document, validate, and correct data-quality issues while preserving the integrity of the original dataset.

## Project Description

This project demonstrates a structured data-quality workflow applied to a 500-record invoice transaction dataset.

The process involved inspecting the raw dataset, identifying data-quality issues, documenting findings, applying evidence-based corrections, retaining unresolved issues for source verification, and performing post-cleaning validation.

## Issues Identified

| Issue | Field | Treatment |
|---|---|---|
| Duplicate Invoice ID | `Invoice_ID` | Retained pending source verification |
| Missing Customer Name | `Customer_Name` | Retained as blank |
| Invalid Quantity | `Quantity` | Retained pending source verification |
| Negative Unit Price | `Unit_Price` | Retained pending source verification |
| Invalid Invoice Date | `Invoice_Date` | Retained pending source verification |
| Discount Rate Anomaly | `Discount_Rate` | Retained as anomaly pending verification |
| Invalid Tax Rate | `Tax_Rate` | Retained pending source verification |
| Missing Customer ID | `Customer_ID` | Retained as blank |
| Incorrect Invoice Total | `Invoice_Total` | Corrected after reconciliation |

Payment Status and Category were inspected and no issue was found under the defined validation rules.

## Validation Results

| Validation Check | Result | Status |
|---|---:|---|
| Invoice Total reconciliation — Row 481 | 1,138,237.06 = 1,138,237.06 | PASS |
| Raw record count | 500 | PASS |
| Processed record count | 500 | PASS |
| Duplicate Invoice ID — `INV-00024` | 2 records documented | DOCUMENTED |
| Missing Customer Name — Row 76 | Blank retained | DOCUMENTED |
| Missing Customer ID — Row 436 | Blank retained | DOCUMENTED |
| Q011 correction | ₦10,000 correction verified | PASS |

## Data Quality Methodology

The dataset was reviewed using field-level validation rules covering uniqueness, completeness, valid ranges, categorical consistency, date validity, and calculated-field reconciliation.

Identified issues were recorded in the Quality Inspection sheet with affected rows, expected rules, and recommended actions.

Corrections were applied only where the correct value could be determined reliably from the available data.

Missing or ambiguous values were retained and documented for source verification rather than being replaced with assumptions.

## Final Outcome

The processed dataset contains 500 invoice records, matching the raw dataset record count.

One confirmed calculation error in `Invoice_Total` was corrected after independent reconciliation. Other identified anomalies and missing or invalid values were retained where sufficient evidence for correction was unavailable.

Final validation confirmed that the corrected invoice total reconciles with its underlying components and that the documented record count was preserved.

## Audit Note

The original raw dataset was preserved separately and was not modified during processing.

The `Quality Inspection` sheet provides the issue log, while the `Processed_Invoice_Data` sheet contains the working dataset and the `Final Validation` sheet documents post-processing checks.
