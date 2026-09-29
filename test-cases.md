# Test Cases - Swag Labs (saucedemo.com)

Executed: 29 September 2026 | Tester: Nikhil Partap Singh | Browser: Chrome, Windows 11

## Login

| ID | Title | Steps | Expected result | Actual result | Status |
|----|-------|-------|-----------------|---------------|--------|
| TC-01 | Login with valid user | 1. Open saucedemo.com 2. Enter `standard_user` / `secret_sauce` 3. Click Login | User lands on inventory page | Landed on /inventory.html | PASS |
| TC-02 | Login with locked-out user | 1. Login with `locked_out_user` / `secret_sauce` | Error shown, user stays on login page | Error: "Epic sadface: Sorry, this user has been locked out." | PASS |
| TC-03 | Login with wrong password | 1. Login with `standard_user` / wrong password | Error shown, no access | Error: "Epic sadface: Username and password do not match any user in this service" | PASS |
| TC-04 | Logout | 1. Login 2. Open menu 3. Click Logout | User returned to login page | Returned to login page | PASS |

## Inventory

| ID | Title | Steps | Expected result | Actual result | Status |
|----|-------|-------|-----------------|---------------|--------|
| TC-05 | Product list display | 1. Login as `standard_user` 2. View inventory page | 6 products shown with name, price and image | 6 products shown with names, prices ($7.99-$49.99) and images | PASS |
| TC-06 | Product images load | 1. Login as `problem_user` 2. Check product images | Each product shows its own correct image | All 6 products show the same placeholder (sl-404) image | FAIL - BUG-01 |
| TC-07 | Sort Name (Z to A) | 1. Login as `problem_user` 2. Select "Name (Z to A)" | Products reorder Z to A | Sort selection reverts to "Name (A to Z)"; order unchanged | FAIL - BUG-02 |

## Cart

| ID | Title | Steps | Expected result | Actual result | Status |
|----|-------|-------|-----------------|---------------|--------|
| TC-08 | Add items to cart | 1. Login as `standard_user` 2. Add Backpack and Bike Light | Cart badge shows 2 | Cart badge showed 2 | PASS |
| TC-09 | Cart contents | 1. Open cart | Both items listed with correct names and prices | Backpack $29.99 and Bike Light $9.99 listed, QTY 1 each | PASS |
| TC-10 | Add to cart per product | 1. Login as `problem_user` 2. Click Add to cart on Backpack, Bike Light, Bolt T-Shirt | All 3 items added | Backpack and Bike Light added; Bolt T-Shirt button did not respond | FAIL - BUG-03 |

## Checkout

| ID | Title | Steps | Expected result | Actual result | Status |
|----|-------|-------|-----------------|---------------|--------|
| TC-11 | Empty checkout form validation | 1. In checkout, click Continue with empty fields | Validation error shown | Error: "First Name is required" | PASS |
| TC-12 | Checkout information | 1. Fill First Name, Last Name, Postal Code 2. Continue | Order overview opens | Overview page opened with both items | PASS |
| TC-13 | Order price calculation | 1. Review overview totals | Item total = sum of item prices; tax and total correct | Item total $39.98 (29.99+9.99), Tax $3.20, Total $43.18 | PASS |
| TC-14 | Complete order | 1. Click Finish | Confirmation page shown | "Thank you for your order!" confirmation shown | PASS |
| TC-15 | Checkout form for problem_user | 1. Login as `problem_user` 2. Add items 3. Open checkout 4. Fill First Name, Last Name, Postal Code 5. Continue | Form accepts input and order overview opens | First Name kept only the last typed character ("h" instead of "Nikhil"); Last Name field rejected all input and stayed empty, blocking checkout with "Error: Last Name is required" (reproduced twice) | FAIL - BUG-04 |
