# Example: REST API — FastAPI GET /products/{id}

PDCA-T applied to a single REST endpoint.

## Scenario
Add product lookup: 200 found, 404 missing, 422 bad input, 401 unauthenticated, < 50ms p99.

## Phase 3: ADR
- ADR-001: Async SQLAlchemy (asyncpg) — FastAPI is async, sync DB calls block event loop

## Phase 4: Tests written first
  test_get_product_existing_id_returns_200
  test_get_product_nonexistent_id_returns_404
  test_get_product_string_id_returns_422
  test_get_product_negative_id_returns_422
  test_get_product_unauthenticated_returns_401
  test_get_product_response_time_under_50ms (benchmark)

## Delivery
6 tests passed, 0 failed, coverage 100%, all CI gates green.
