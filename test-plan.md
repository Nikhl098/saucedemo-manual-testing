# Test Plan - Swag Labs (saucedemo.com)

## 1. Objective

Verify the core user journeys of the Swag Labs demo e-commerce application: login, product browsing, sorting, cart and checkout. Identify and document defects with reproducible steps.

## 2. Application under test

- URL: https://www.saucedemo.com
- Type: demo e-commerce web application (public QA practice site by Sauce Labs)

## 3. Scope

**In scope**
- Login: valid credentials, invalid password, locked-out user, problem user
- Inventory page: product list, names, prices, images
- Sorting: Name (A to Z), Name (Z to A), Price (low to high), Price (high to low)
- Cart: add item, cart badge count, cart contents, remove item
- Checkout: information form validation, order overview price calculation, order completion
- Logout

**Out of scope**
- Performance/load testing
- Security testing
- Mobile viewports
- Payment processing (demo app has no real payments)

## 4. Approach

- Manual, scripted functional testing based on the test cases in `test-cases.md`
- Black-box testing from the end-user perspective
- Each test case executed once; actual result recorded against expected result
- Defects logged in `bug-report.md` with severity, steps to reproduce and evidence

## 5. Test environment

- Browser: Chrome (latest), desktop viewport
- OS: Windows 11
- Network: stable broadband

## 6. Test data

Demo users published on the application login page:
- `standard_user` / `secret_sauce`
- `locked_out_user` / `secret_sauce`
- `problem_user` / `secret_sauce`

Checkout form data: Nikhil / Singh / 110075

## 7. Entry criteria

- Application reachable and login page loads
- Test cases reviewed and ready

## 8. Exit criteria

- All 15 planned test cases executed
- All defects logged with steps to reproduce
- Test summary report prepared

## 9. Deliverables

- Test cases with actual results (`test-cases.md`)
- Bug report (`bug-report.md`)
- Test summary report (`test-summary.md`)
