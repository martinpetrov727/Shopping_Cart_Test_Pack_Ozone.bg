## Manual Test Pack – Shopping Cart & Checkout Flow  
App/Site: https://www.ozone.bg/  
Date: 05.03.2026  
Tester: Martin Petrov  

---

## Scope
Testing the shopping cart and checkout functionality for both guest and registered users.

---

## Test Cases

### TC-001 - Add item to shopping cart
Preconditions:
- User is on the ozone.bg website

Steps:
1. Navigate to a category
2. Select a product
3. Click "Buy" / "Add to cart"

Expected Result:
- Product is successfully added to the shopping cart


### TC-002 - Update item quantity (valid value)
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Set quantity to 4

Expected Result:
- Quantity is updated to 4
- Total price is updated accordingly


### TC-003 - Update item quantity beyond stock
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Set quantity to 100

Expected Result:
- Quantity is not updated beyond available stock
- Error message is displayed
- Total price is not updated


### TC-004 - Update quantity with negative value
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Enter quantity "-1"

Expected Result:
- Quantity resets to default (e.g., 1)
- Invalid value is not accepted


### TC-005 - Update quantity with non-numeric value
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Enter "A" in quantity field

Expected Result:
- Input is rejected OR reset to valid value
- System prevents invalid input


### TC-006 - Update quantity to zero
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Set quantity to "0"

Expected Result:
- Item is removed from the cart
- Cart is updated accordingly


### TC-007 - Apply valid promo code
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Enter valid promo code
3. Click "Apply promo code"

Expected Result:
- Discount is applied
- Total price is reduced


### TC-008 - Apply invalid promo code
Preconditions:
- Item is added to the shopping cart

Steps:
1. Open shopping cart
2. Enter invalid promo code
3. Click "Apply promo code"

Expected Result:
- Error message is displayed
- Discount is not applied


### TC-009 - Successful checkout
Preconditions:
- Item is in cart
- User is registered

Steps:
1. Open shopping cart
2. Click "Checkout"
3. Log in
4. Enter valid address
5. Select delivery method
6. Select payment method
7. Click "Place order"

Expected Result:
- Order is successfully placed
- Confirmation email is sent


### TC-010 - Checkout with missing address
Preconditions:
- Item is in cart
- User is registered

Steps:
1. Open shopping cart
2. Click "Checkout"
3. Log in
4. Leave address empty
5. Complete other fields
6. Click "Place order"

Expected Result:
- Order is not placed
- Error message is displayed for missing address


### TC-011 - Apply expired coupon
Preconditions:
- Item is in cart

Steps:
1. Open shopping cart
2. Enter expired coupon code
3. Click "Apply"

Expected Result:
- Coupon is not applied
- Error message: "Coupon code is expired"


### TC-012 - Remove applied coupon
Preconditions:
- Coupon is already applied

Steps:
1. Open shopping cart
2. Click "Remove coupon"

Expected Result:
- Coupon is removed
- Total price is updated


### TC-013 - Cart persistence after page refresh
Preconditions:
- Item is added to cart

Steps:
1. Refresh the browser

Expected Result:
- Item remains in the cart


### TC-014 - Cart persistence after browser restart
Preconditions:
- Item is added to cart

Steps:
1. Close browser
2. Reopen website
3. Open cart

Expected Result:
- Item remains in the cart


### TC-015 - Cart persistence after login
Preconditions:
- Item is added to cart as guest
- User has an account

Steps:
1. Add item to cart as guest
2. Log in to account
3. Open cart

Expected Result:
- Item remains in the cart after login