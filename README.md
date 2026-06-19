# 🛒 E-Commerce Platform  Manual Testing Project

## 📌 Project Overview
This repository showcases a comprehensive manual testing suite for a standard E-Commerce web application (Focus Areas: User Authentication, Product Search, and Cart Management). The objective is to demonstrate the end-to-end Software Testing Life Cycle (STLC) documentation, including Test Cases and Bug Reports.

---

## 📑 1. Test Cases Suite
### Component: User Authentication (Login / Signup)
| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC_AUTH_001 | Verify successful login with valid credentials. | User is registered. | 1. Navigate to Login page.<br>2. Enter valid email and password.<br>3. Click 'Login'. | User should be redirected to the dashboard. | **PASSED** |
| TC_AUTH_002 | Verify login fails with an invalid password. | User is registered. | 1. Navigate to Login page.<br>2. Enter valid email but wrong password.<br>3. Click 'Login'. | Error message "Invalid credentials" should appear. | **PASSED** |

### Component: Cart Management
| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC_CART_001 | Verify 'Add to Cart' increases cart count. | Product is in stock. | 1. Open a product page.<br>2. Click 'Add to Cart'. | Cart badge count should increase by 1. | **PASSED** |
| TC_CART_002 | Verify 'Add to Cart' for an Out-of-Stock product. | Product is out of stock. | 1. Open out-of-stock product.<br>2. Check 'Add to Cart' button. | Button should be disabled or show "Out of Stock". | **FAILED** |

---

## 🐛 2. Bug Reports Ledger (Jira Style)

### Bug ID: BUG_CART_002
* **Title:** 'Add to Cart' button is active for Out-of-Stock items.
* **Severity:** High | **Priority:** High
* **Environment:** Production (Chrome v120.0)
* **Steps to Reproduce:**
  1. Navigate to the electronics category.
  2. Click on "Wireless Headphones" (Marked as Out of Stock).
  3. Observe the "Add to Cart" button.
* **Expected Result:** The button should be disabled, preventing the user from adding it to the cart.
* **Actual Result:** The button is clickable, and the product is successfully added to the cart, causing a checkout crash.
* **Status:** Open
