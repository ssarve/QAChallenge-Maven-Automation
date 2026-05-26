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

## How to Import in Eclipse

1. Extract the ZIP file.
2. Open Eclipse.
3. Go to `File > Import`.
4. Select `Maven > Existing Maven Projects`.
5. Click `Next`.
6. Browse and select the extracted `QAChallenge_Maven_Eclipse` folder.
7. Ensure `pom.xml` is selected.
8. Click `Finish`.
9. Wait for Maven dependencies to download.

## How to Run Tests in Eclipse

Option 1:

1. Right-click the project.
2. Select `Run As > Maven test`.

Option 2:

1. Open any test class under `src/test/java`.
2. Right-click inside the class.
3. Select `Run As > JUnit Test`.

## How to Run from Command Line

```bash
mvn clean test
```

## Important Note

The original assignment specifically asks for XCTest/XCUITest on macOS/Xcode. This Maven project is a converted QA solution for Eclipse and validates the same core functional requirements at service/business-logic level.


## HTML Reporting Added

This project now includes ExtentReports integration for a professional HTML execution report.

### Run tests and generate Extent Report

```bash
mvn clean test
```

After execution, open this file in any browser:

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

### Eclipse steps

1. Right click the project.
2. Select `Maven > Update Project`.
3. Right click the project again.
4. Select `Run As > Maven test`.
5. Refresh the project.
6. Open `target/extent-reports/QAChallengeAutomationReport.html`.
