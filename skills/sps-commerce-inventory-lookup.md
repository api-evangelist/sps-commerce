---
name: sps-commerce-inventory-lookup
description: Look up SPS Commerce inventory items by partner and product identifiers, then fetch a single item by spsItemId.
api: openapi/sps-commerce-inventory-api-openapi.yml
operations:
  - v1-items-get
  - v1-items-get-by-id
generated: '2026-10-09'
method: generated
---
# Inventory lookup

Servers: `https://integration.api.spscommerce.com` (integration) and `https://api.spscommerce.com` (prod). Auth: bearer token (`SpsBearer`).

1. Call `v1-items-get` (`GET /inventory/v1/items`) with any of `partnerId`, `buyerPartNumber`, `vendorPartNumber`, `manufacturerPartNumber`, `upc`, `gtin`, `sku`, `ean`, `ndc`, `quantityUpdatedSince`. Page with `offset` / `limit`.
2. For a specific result, call `v1-items-get-by-id` (`GET /inventory/v1/items/{spsItemId}`); the spec marks this operation internal.
3. Errors: 400 for bad input, 404 when the item is not found, 500 server error. GETs are safe to retry.
