# Test Cases — E-Commerce Checkout Flow

| ID | Title | Priority | Preconditions |
|---|---|---|---|
| TC-01 | Guest checkout completes with valid shipping + test card | High | Cart has 1 item; on cart page |
| TC-02 | Checkout blocked when cart is empty | Medium | Cart is empty |
| TC-03 | Invalid email format is rejected | High | On shipping form |
| TC-04 | Required-field validation fires on empty submit | High | On shipping form |
| TC-05 | Order totals calculate correctly (subtotal + tax + shipping) | High | Cart has 2 items with known prices |
| TC-06 | Valid promo code applies discount | Medium | Valid promo code available |
| TC-07 | Invalid promo code shows clear error | Medium | On payment step |
| TC-08 | Declined test card shows graceful error, no order created | High | Declined test card number |
| TC-09 | Order confirmation page shows order number | High | Valid checkout (TC-01 path) |
| TC-10 | Confirmation email is received after order | Medium | Valid checkout; access to inbox |
| TC-11 | Double-clicking "Place Order" creates only one order | High | Valid checkout; slow network |
| TC-12 | Back button during payment does not lose cart data | Low | Items in cart, on payment step |

## TC-01 — Guest checkout completes (detailed example)

**Steps**
1. Add one item to the cart and go to checkout as a guest.
2. Enter valid shipping details (name, address, city, ZIP, valid email).
3. Enter a valid test card number, expiry, and CVC.
4. Click "Place Order".

**Expected result**
- Order confirmation page displays with an order number.
- Cart is emptied.
- Confirmation email arrives within 5 minutes.

## TC-11 — Double-click protection (detailed example)

**Steps**
1. Complete shipping and payment details with a valid test card.
2. Throttle network (or click "Place Order" twice in rapid succession).

**Expected result**
- Exactly one order is created (one order number, one charge).
- UI disables the button after the first click or dedupes the request.
