# Test Summary Report - Swag Labs (saucedemo.com)

**Project:** Manual testing of Swag Labs demo e-commerce app
**Tester:** Nikhil Partap Singh
**Execution date:** 29 September 2026
**Environment:** Chrome (latest), Windows 11, desktop viewport

## Execution results

| Metric | Count |
|---|---|
| Test cases planned | 15 |
| Test cases executed | 15 |
| Passed | 11 |
| Failed | 4 |
| Blocked / not run | 0 |
| Pass rate | 73% |
| Defects logged | 4 (2 Critical, 2 Major) |

## Results by module

| Module | Cases | Pass | Fail |
|---|---|---|---|
| Login & logout | 4 | 4 | 0 |
| Inventory & sorting | 3 | 1 | 2 |
| Cart | 3 | 2 | 1 |
| Checkout | 5 | 4 | 1 |

## Key observations

- All core business flows (login, add to cart, full checkout with correct price calculation, order confirmation) work correctly for a normal user.
- All 4 failures are isolated to the `problem_user` account, where the demo application intentionally seeds defects. This account is useful negative-test data.
- Checkout price calculation verified manually: item total $39.98, tax $3.20 (8%), final total $43.18 - all correct.

## Conclusion

The application's happy path is stable. Defects found are documented with reproduction steps in `bug-report.md`. Recommend re-testing the inventory module (images, sorting, add-to-cart) and the checkout information form after fixes.
