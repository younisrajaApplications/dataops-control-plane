# Orders Dataset Schema

## Purpose

The orders dataset represents generic business order data.

It is used as the first sample dataset for the DataOps Control Plane.

## Columns

| Column | Type | Required | Description |
|---|---|---|---|
| order_id | string | yes | Unique order identifier |
| customer_id | string | yes | Customer identifier |
| order_timestamp | timestamp | yes | Time the order was placed |
| product_id | string | yes | Product identifier |
| quantity | integer | yes | Number of units ordered |
| unit_price | decimal | yes | Price per unit |
| currency | string | yes | Order currency |
| country | string | yes | Order country |
| order_status | string | yes | Current order status |

## Allowed Status Values

- CREATED
- PAID
- CANCELLED
- REFUNDED
- SHIPPED

## Validation Rules

- `order_id` must not be empty
- `customer_id` must not be empty
- `product_id` must not be empty
- `quantity` must be greater than zero
- `unit_price` must be greater than zero
- `currency` must be one of GBP, USD or EUR
- `order_status` must be one of the allowed status values
- `order_timestamp` must not be in the future