# ETL Validation Framework - AWS Glue

## Project Overview
Automated ETL validation framework built on AWS
to validate data pipeline quality.

## Architecture
Raw Data (S3) → AWS Glue Job → Processed Data (S3)
                                      ↓
                            Validation Framework
                                      ↓
                            Validation Report

## Tech Stack
- AWS Glue (PySpark)
- Amazon S3
- AWS CloudWatch
- Python / Pandas / boto3

## ETL Pipeline
- Source: E-Commerce Sales CSV (541,909 records)
- Transformations Applied:
  - Removed NULL CustomerIDs
  - Filtered negative Quantity & Price
  - Calculated TotalAmount
  - Added CustomerSegment (High/Mid/Low Value)
  - Removed duplicates
- Target: Parquet format (387,841 clean records)

## Validation Test Cases
| Test Case | Result |
|-----------|--------|
| Record Count Check | ✅ PASS |
| NULL CustomerID Check | ✅ PASS |
| Negative Quantity Check | ✅ PASS |
| Negative Price Check | ✅ PASS |
| Segment Validation | ✅ PASS |

## Results
- 154,068 invalid records filtered out (28%)
- 0 NULL values in target
- 0 negative values in target
- 3 customer segments correctly assigned
