# QA Challenge Maven Eclipse Solution

## Project Type

This is a Java Maven JUnit 5 test automation equivalent of the original iOS SwiftUI/XCTest assignment.

The original assignment is an Xcode project and cannot be natively executed in Eclipse. Since the requested working environment is Eclipse, this solution converts the app's business requirements into a Maven-based Java test project that can be imported and executed from Eclipse.

## Tech Stack

- Java 17
- Maven
- JUnit 5
- AssertJ
- Eclipse IDE compatible

## Covered Functional Areas

- Valid and invalid login
- Product category filtering
- Product name search
- Combined category and search filtering
- Out-of-stock cart restriction
- Cart quantity increment
- Cart item removal when quantity reaches zero
- Promo code SAVE10 discount calculation
- Checkout mandatory field validation
- Valid checkout confirmation and cart clearing

## Important Note

The original assignment specifically asks for XCTest/XCUITest on macOS/Xcode. This Maven project is a converted QA solution for Eclipse and validates the same core functional requirements at service/business-logic level.

## High-Level Architecture
The framework structure looks like this:
QAChallenge_Maven_Eclipse_Solution
│
├── pom.xml
├── src
│   └── test
│       └── java
│           └── tests
│               ├── LoginTest.java
│               ├── CartTest.java
│               ├── PromoCodeTest.java
│               └── CheckoutTest.java
│
├── target
│   └── extent-reports
│       └── QAChallengeAutomationReport.html

## Framework Layering
Layer 1 — Test Layer
Contains:
Test classes
Examples:
•	LoginTest
•	CartTest
________________________________________
Layer 2 — Business Logic Layer
Contains:
Validation logic
Examples:
•	Discount calculation
•	Cart total
•	Authentication rules
________________________________________
Layer 3 — Reporting Layer
Contains:
ExtentReports
________________________________________
Layer 4 — Build Layer
Contains:
Maven

## HTML Reporting Added

This project includes ExtentReports integration for a professional HTML execution report.

### Run tests and generate Extent Report

```bash
mvn clean test
```
```text
target/extent-reports/QAChallengeAutomationReport.html
```

### Optional Maven Surefire HTML report

```bash
mvn surefire-report:report
```

Then open:

```text
target/site/surefire-report.html
```
