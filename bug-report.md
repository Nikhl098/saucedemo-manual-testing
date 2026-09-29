# Bug Report - Swag Labs (saucedemo.com)

Found during manual execution on 29 September 2026 by Nikhil Partap Singh.
Browser: Chrome, Windows 11.

---

## BUG-01: Product images broken for problem_user

- **Severity:** Major
- **Module:** Inventory page
- **Found in test case:** TC-06

**Steps to reproduce**
1. Log in as `problem_user` / `secret_sauce`
2. View the inventory page

**Expected:** Each product displays its own product image.
**Actual:** All 6 product images load the same placeholder file (`sl-404` image). No real product image is shown.

---

## BUG-02: Product sorting does not work for problem_user

- **Severity:** Major
- **Module:** Inventory page - sort control
- **Found in test case:** TC-07

**Steps to reproduce**
1. Log in as `problem_user` / `secret_sauce`
2. In "Sort products", select "Name (Z to A)"

**Expected:** Product list reorders from Z to A and the selection stays.
**Actual:** The selection immediately reverts to "Name (A to Z)" and the product order never changes.

---

## BUG-03: Add to cart does not respond on specific products for problem_user

- **Severity:** Critical (blocks purchase)
- **Module:** Inventory page - Add to cart
- **Found in test case:** TC-10

**Steps to reproduce**
1. Log in as `problem_user` / `secret_sauce`
2. Click "Add to cart" on Sauce Labs Backpack (works), Sauce Labs Bike Light (works), then Sauce Labs Bolt T-Shirt

**Expected:** Every product's Add to cart button adds the item and the cart badge increments.
**Actual:** The Sauce Labs Bolt T-Shirt button does not respond; the item is never added and the cart badge stays at 2.

---

## BUG-04: Checkout information form rejects input for problem_user - checkout blocked

- **Severity:** Critical (checkout impossible)
- **Module:** Checkout - Your Information
- **Found in test case:** TC-15

**Steps to reproduce**
1. Log in as `problem_user` / `secret_sauce`
2. Add any product to the cart and open Checkout
3. Fill First Name "Nikhil", Last Name "Singh", Zip/Postal Code "110075"
4. Click Continue

**Expected:** Form accepts the values and the order overview opens.
**Actual:** First Name retains only the last typed character ("h" instead of "Nikhil"). Last Name rejects all input and stays empty, so submit fails with "Error: Last Name is required". The order cannot be completed. Reproduced twice in a row.

---

## Notes

- The same flows pass for `standard_user`, so the defects are isolated to the `problem_user` account (the demo app intentionally seeds defects in this account).
- All three defects reproduced consistently on repeat attempts.
