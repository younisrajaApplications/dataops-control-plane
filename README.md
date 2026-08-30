# DataOps Control Plane

A reusable data ingestion and quality platform for validating, tracking and publishing trusted business data.

## Overview

DataOps Control Plane is a hands-on engineering project designed to simulate a reusable data platform.

The platform ingests business datasets, validates records, separates accepted and rejected rows, persists operational metadata, runs SQL data quality checks and prepares trusted data for a warehouse layer.

The project is designed around common data platform patterns rather than a single fixed dataset. The first sample dataset is orders, with the architecture intended to support additional dataset types over time.

## Problem Statement

Organisations often receive data from multiple source systems.

Before that data can be trusted for reporting, analytics or downstream processing, it needs to be validated, reconciled and made auditable.

This project solves a simplified version of that problem by building a reusable ingestion and quality control platform.

The core question the platform answers is:

```text
Can this data be trusted after it has been ingested?
```

## Planned Capabilities

- dataset registration
- CSV file ingestion
- schema and rule validation
- accepted and rejected output generation
- ingestion audit history in Postgres
- SQL data quality checks
- CI-friendly quality gates
- Jenkins pipeline-as-code
- BigQuery raw, curated and mart warehouse layers
- Terraform-managed cloud resources

## Tech Stack

- Java
- Spring Boot
- Maven
- Postgres
- Flyway
- SQL
- Docker Compose
- Bash
- Jenkins
- GitHub
- Terraform
- GCP BigQuery

## Architecture

```text
Business data file
        ↓
Dataset Registry
        ↓
Spring Boot Ingestion API
        ↓
Validation Engine
        ↓
Accepted / Rejected Outputs
        ↓
Postgres Operational Audit Store
        ↓
SQL Data Quality Checks
        ↓
BigQuery Raw Layer
        ↓
BigQuery Curated Layer
        ↓
BigQuery Mart Layer
        ↓
Jenkins CI/CD Quality Gates
```

## Repository Structure

```text
dataops-control-plane/
├── app/
├── data/
│   ├── sample/
│   ├── processed/
│   └── schemas/
├── docs/
│   └── decisions/
├── jenkins/
├── scripts/
├── sql/
│   ├── postgres/
│   │   └── data-quality/
│   └── bigquery/
│       ├── ddl/
│       └── transformations/
└── terraform/
```

### Key Folders

- `app/` contains application code.
- `data/` contains sample files, schemas and generated local outputs.
- `docs/` contains project documentation and architecture decisions.
- `jenkins/` contains Jenkins-related documentation.
- `scripts/` contains repeatable local and CI helper scripts.
- `sql/postgres/` contains Postgres quality checks.
- `sql/bigquery/` contains BigQuery DDL and transformation SQL.
- `terraform/` contains future infrastructure-as-code configuration.

## Current Status

Project foundation in progress.

The initial project setup includes:

- repository structure
- documentation structure
- sample dataset schema
- sample input file
- initial architecture documentation
- first architecture decision record

## Future Improvements

- configurable validation rules
- multiple dataset support
- Postgres-backed ingestion audit store
- SQL data quality checks
- BigQuery loading
- Terraform-managed warehouse resources
- Jenkins end-to-end validation
- reporting marts