# Invoice Data Quality & Cleaning

A portfolio project demonstrating a structured invoice data-quality workflow using Microsoft Excel.

## Project Overview

This project applies data-quality inspection, issue documentation, evidence-based correction, and post-cleaning validation to a 500-record invoice transaction dataset.

The workflow was designed to preserve the original data, make only defensible corrections, and retain unresolved or ambiguous issues for source/business verification rather than inventing replacement values.

## Objectives

- Inspect invoice data for quality issues.
- Identify duplicate, missing, invalid, inconsistent, and calculation-related records.
- Document each issue with an expected data-quality rule and affected row.
- Apply corrections only where the correct value can be established reliably.
- Validate the processed dataset after cleaning.
- Produce an auditable Excel workflow suitable for professional data-cleaning work.

## Dataset

- **Records:** 500 invoice transactions
- **Tool:** Microsoft Excel
- **Dataset type:** Invoice transaction data

> **Data privacy:** Only synthetic or otherwise non-sensitive data should be published in this public repository. Do not upload real customer personal information such as names, email addresses, phone numbers, or customer IDs.

## Data Quality Issues Reviewed

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

Payment Status and Category were also inspected and no issue was found under the defined validation rules.

## Cleaning Approach

The workbook uses a controlled workflow:

1. Preserve the raw dataset.
2. Inspect fields against defined quality rules.
3. Record findings in `Quality Inspection`.
4. Process the working dataset in `Processed_Invoice_Data`.
5. Correct only confirmed or independently calculable errors.
6. Retain ambiguous or missing values when the correct replacement cannot be established.
7. Validate the processed data in `Final Validation`.
8. Summarize the methodology and outcome in `Data Quality Summary`.

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

## Workbook Structure

The Excel workbook contains:

- `Raw_Invoice_Data` — preserved source dataset.
- `Quality Inspection` — field-level issue log and investigation actions.
- `Processed_Invoice_Data` — working dataset after documented processing decisions.
- `Final Validation` — post-processing validation checks.
- `Data Quality Summary` — project overview, issue treatment, methodology, validation results, and audit notes.

## Key Data-Quality Principle

A data-cleaning process should not create information that the source does not support. Where a value could not be reliably corrected, it was retained or left blank and documented for verification.

## Files

The repository is organized into raw data, processed data, documentation, and supporting screenshots so that the workflow can be reviewed independently.

## Tools

- Microsoft Excel
- GitHub
- Data quality inspection and validation techniques

## Portfolio Relevance

This project demonstrates practical skills in:

- Data cleaning
- Data quality assurance
- Excel data validation
- Duplicate detection
- Missing-value handling
- Data-rule definition
- Formula reconciliation
- Audit documentation
- Quality-control reporting
