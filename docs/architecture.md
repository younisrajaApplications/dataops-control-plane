# Architecture

## Purpose

DataOps Control Plane is designed as a reusable ingestion and data quality platform.

The platform separates operational ingestion tracking from analytical warehouse processing.

## High-Level Flow

```text
Input file
    ↓
Dataset metadata lookup
    ↓
Validation engine
    ↓
Accepted and rejected outputs
    ↓
Postgres audit store
    ↓
SQL quality checks
    ↓
BigQuery warehouse layers
```

## Core Components
### Spring Boot Ingestion Service

Handles API requests, file uploads, validation orchestration and ingestion status queries.

### Dataset Registry

Stores metadata about supported datasets, including dataset name, expected schema and validation rules.

### Validation Engine

Applies validation rules to incoming records and decides whether each row is accepted or rejected.

### Postgres Operational Store

Stores ingestion runs, accepted record metadata, rejected records and quality check results.

### SQL Quality Layer

Runs post-ingestion checks to verify stored data is complete, valid and explainable.

### BigQuery Warehouse

Stores trusted analytical data using raw, curated and mart layers.

### Jenkins Pipeline

Runs tests, migrations, end-to-end checks and SQL quality gates.

### Terraform

Provisions future BigQuery datasets, tables and cloud resources.

### Design Principles
- sector-neutral design
- local-first development
- repeatable workflows
- pipeline-friendly validation
- clear audit trail
- separation of operational and analytical storage
- infrastructure as code