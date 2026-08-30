# Requirements

## Functional Requirements

The platform should:

1. Allow datasets to be registered.
2. Accept data files for registered datasets.
3. Validate uploaded records against dataset rules.
4. Separate accepted and rejected records.
5. Store ingestion metadata in Postgres.
6. Store rejection reasons for invalid records.
7. Generate reconciliation evidence for ingestion runs.
8. Expose APIs for querying ingestion history.
9. Run SQL data quality checks after ingestion.
10. Support future loading into BigQuery.
11. Support CI/CD validation through Jenkins.
12. Support future infrastructure provisioning through Terraform.

## Non-Functional Requirements

The platform should be:

- maintainable
- testable
- auditable
- repeatable
- local-first
- zero-cost during development
- suitable for CI/CD automation
- designed for future cloud deployment

## Out of Scope for Initial Version

- authentication
- production-grade security
- real cloud deployment
- live streaming ingestion
- UI dashboard
- advanced orchestration tools