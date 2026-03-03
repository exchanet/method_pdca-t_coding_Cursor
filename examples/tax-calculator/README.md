# Example: Tax Calculator / Calculadora de Impuestos

Full PDCA-T worked example. See METHOD.md for complete methodology.

## Scenario
VAT calculation service: configurable rate, EUR/USD/GBP, bulk support, Decimal only.

## Phase 1
Objective: calculate_vat() and bulk_calculate_vat() for a billing system.
Out of scope: invoice PDF, database layer.

## Phase 2: Requirements
- FR-01: VAT at configurable rate
- FR-02: EUR, USD, GBP support  
- FR-03: ValueError for price <= 0
- FR-04: ValueError for rate outside [0,1]
- FR-05: TypeError for non-Decimal input
- FR-06: Bulk calculate for list of prices
- NFR-01: decimal.Decimal (not float)
- NFR-02: Thread-safe pure functions, < 1ms/call

## Phase 3: ADRs
- ADR-001: Decimal over float (33.33*0.21 in float = 6.999300000000001)
- ADR-002: Pure functions over Calculator class (no shared state)

## Phase 4: Tests first (12 tests), then implementation

Tests written first:
  test_standard_vat_eur / test_standard_vat_usd / test_zero_vat_rate
  test_minimum_price / test_negative_price_raises / test_zero_price_raises
  test_rate_above_one_raises / test_float_input_raises_type_error
  test_invalid_currency_raises / test_bulk_happy_path
  test_bulk_empty_list / test_bulk_performance

## Delivery Report
- 12 tests passed, 0 failed, coverage 100%, time 0.31s
- ADR-001 and ADR-002 accepted
- No technical debt registered
- All CI gates green
