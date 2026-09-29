# Swag Labs (saucedemo.com) - Manual Testing Project

Manual testing of the Swag Labs demo e-commerce application (https://www.saucedemo.com), a public practice site maintained by Sauce Labs for QA learning.

**Author:** Nikhil Partap Singh - Manual QA Tester (Fresher)
**Date executed:** 29 September 2026

## Scope

- Login functionality (valid, invalid, locked-out and problem users)
- Product inventory display and sorting
- Add to cart / cart contents
- End-to-end checkout flow, including field validation and price calculation

## Artifacts

| File | Contents |
|---|---|
| `test-plan.md` | Test plan: objectives, scope, approach, entry/exit criteria |
| `test-cases.md` | 15 test cases with steps, expected and actual results |
| `bug-report.md` | 4 defects found and reproduced during execution |
| `test-summary.md` | Execution summary: 15 cases, 11 passed, 4 failed |

## Summary of findings

All core flows pass for `standard_user`. Four defects were found and reproduced with the `problem_user` account: broken product images, product sorting not working, Add to cart failing on specific products, and the checkout form rejecting input so no order can be completed. Details in `bug-report.md`.

## Environment

- Browser: Chrome (latest), desktop viewport
- OS: Windows 11
- Test data: demo users published on saucedemo.com (`standard_user`, `locked_out_user`, `problem_user`)
