# TEST_NOTES

## Tested Scenarios

1. Valid login with `qa@example.com / Password123` signs in successfully.
2. Invalid login keeps the user signed out and returns a helpful error message.
3. Category filter returns only products from the selected category.
4. Product search filters inventory by product name.
5. Category and search filters work together.
6. Out-of-stock products are not added to the cart.
7. Adding the same product multiple times increases quantity.
8. Removing quantity to zero removes the item from cart.
9. Promo code `SAVE10` applies a 10% discount.
10. Checkout requires full name, valid email, five-digit ZIP, accepted terms, and a non-empty cart.
11. Valid checkout displays confirmation and clears the cart.

## Defects Found in Original Swift Code

### DEF-001: SAVE10 applies only 5% discount instead of 10%

Original requirement:

- Promo code `SAVE10` should discount the cart subtotal by 10%.

Observed in original `ShopViewModel.swift`:

```swift
return subtotal * Decimal(0.05)
```

Expected:

```swift
return subtotal * Decimal(0.10)
```

Impact:

- Customers receive incorrect discount.
- Checkout total is higher than expected.
- Revenue and promotion reporting may become inaccurate.

Severity: Medium
Priority: High

## Flake Risks in Original iOS Automation

1. Inventory loading is asynchronous after login.
2. UI tests should wait for stable inventory elements instead of using fixed sleep.
3. SwiftUI segmented picker behavior may vary depending on simulator/iOS version.
4. Keyboard focus can interfere with typing and tapping fields in iOS UI tests.

## Suggested Testability Improvements

1. Add accessibility identifiers for product category text and product row containers.
2. Add explicit accessibility identifiers for checkout validation messages.
3. Add deterministic test data seeding for all products and cart states.
4. Add clearer disabled-state identifiers or labels for sold-out product buttons.
5. Add direct app state reset between UI tests to avoid dependency between tests.

## Scope Not Covered

1. Native XCTest/XCUITest execution was not performed because this Eclipse-compatible solution does not run the iOS app.
2. Visual UI validations and simulator-specific flows are not covered in this Maven conversion.
3. Network/API testing is not applicable because the provided app uses local static data.

## Rationale for Converted Approach

The assignment project is a native iOS SwiftUI/Xcode project. Eclipse cannot build or execute `.xcodeproj` files. To provide a working QA deliverable in Eclipse, the key product rules were converted into a Java Maven test suite with maintainable test classes and clear assertions.
