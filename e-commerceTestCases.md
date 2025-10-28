# Test Cases for E-Commerce Checkout Flow

**Feature:** Checkout Process
**Scope:** From clicking "Proceed to Checkout" to "Order Confirmation."

| TC ID | Test Type | Scenario | Test Step | Expected Result | Pass/Fail | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **C-001** | Positive | Item(s) in cart. User logged in. | 1. Click 'Proceed to Checkout'. <br> 2. Fill all required shipping fields with valid data. <br> 3. Select 'Credit Card' and input valid details. <br> 4. Click 'Place Order'. | User is redirected to the **Order Confirmation** page. An order number is displayed. Confirmation email is sent. | | **Happy Path** |
| **C-002** | Negative | Item(s) in cart. User not logged in. | 1. Click 'Proceed to Checkout'. <br> 2. Leave **'Shipping Address Line 1'** blank. <br> 3. Fill other fields with valid data. <br> 4. Click 'Continue/Next Step'. | An immediate, clear **validation error message** appears for the missing field. User is prevented from proceeding. | | **Error Handling** |
| **C-003** |  | Item(s) in cart. Guest user. | 1. Click 'Proceed to Checkout'. <br> 2. In the shipping form, enter a **PO Box** as the shipping address. <br> 3. Proceed to payment and place the order. | If PO Box shipping is unsupported: A clear, explicit error message is displayed stating PO Boxes are not allowed. <br> If supported: Order is placed successfully. | | **Boundary Condition** |
| **C-004** | Negative | Item(s) in cart. | 1. Navigate to the Payment step. <br> 2. Input an **expired credit card number** (valid format). <br> 3. Click 'Place Order'. | A clear error message stating **"Card Expired"** is displayed. Order is not processed. | | **Invalid Data** |
| **C-005** | Positive (Data Integrity) | Item(s) in cart. | 1. Review the order summary on the final confirmation step. <br> 2. Verify that the **total price** (item price + tax + shipping) matches the calculated sum from the cart. | The final displayed total price is accurate and matches the pre-checkout summary. **Data integrity** is maintained. | | **Financial Check** |
