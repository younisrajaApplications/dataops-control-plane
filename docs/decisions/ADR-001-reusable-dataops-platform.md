# ADR-001: Build a Reusable DataOps Platform

## Status

Accepted

## Context

The project is designed to demonstrate a reusable approach to data ingestion, validation, quality checking and warehouse publishing.

Rather than building a workflow that is tightly coupled to one business domain, the platform should support generic business datasets such as orders, customers, products and inventory.

This allows the architecture to focus on common data platform concerns:

- dataset registration
- file ingestion
- validation rules
- accepted and rejected records
- ingestion audit history
- SQL quality checks
- warehouse publishing

## Decision

Build a reusable DataOps platform that supports generic dataset ingestion, validation, quality checking and warehouse publishing.

The first sample dataset will be orders, but the platform should be designed so additional datasets can be introduced later without changing the overall architecture.

## Consequences

### Benefits

- creates a more reusable architecture
- keeps the platform focused on common data engineering patterns
- avoids hardcoding the system around one dataset type
- supports future extension to multiple datasets
- makes validation logic easier to evolve over time
- provides a clearer separation between platform behaviour and sample data

### Trade-offs

- slightly more design complexity
- requires a dataset registry concept
- validation needs to become configurable rather than hardcoded
- initial implementation may take longer than a single-purpose ingestion service