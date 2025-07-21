# playwright-sample-project

## **Overview:**

This is a sample Automation project using Playwright and Typescript, utilizing the Playwright test runner to execute test cases. It is a Data Driven framework focused on separating test script logic from test data, allowing the creation of robust automation scripts with different sets of test data. Test data is maintained in an external Excel sheet, which the scripts connect to for data-driven execution. This approach significantly reduces the number of test scripts needed for multiple data sets compared to modular frameworks.
---

## **Project Structure**

```
playwright-sample-project/
├── src/
│   ├── advantage/         # UI test logic, page objects, and constants
│   │   ├── constants/     # UI and page-specific constants
│   │   ├── pages/         # Page Object Model classes for UI
│   │   └── steps/         # Step definitions for UI flows
│   ├── API/
│   │   ├── REST/          # REST API test logic and constants
│   │   └── SOAP/          # SOAP API test logic and constants
│   ├── database/          # Database test logic and constants
│   ├── framework/
│   │   ├── config/        # Base test configuration
│   │   ├── constants/     # Shared framework constants
│   │   ├── logger/        # Logging and test listener utilities
│   │   ├── manager/       # Suite and browser management
│   │   ├── playwright/    # Playwright-specific actions, API, and assertions
│   │   ├── reporter/      # Reporting integrations (Allure, HTML, etc.)
│   │   ├── template/      # Suite template generator
│   │   └── utils/         # Utility classes (Excel, PDF, DB, CLI, etc.)
│   ├── resources/
│   │   ├── API/           # API request payloads (JSON/XML)
│   │   └── data/          # Test data (Excel)
│   └── tests/             # Test specifications (UI, API, DB)
├── playwright.config.ts   # Playwright configuration
├── package.json           # Project dependencies and scripts
└── README.md              # Project documentation
```

---

## **Key Utilities & Advanced Features**

- **ExcelUtil**: Reads test data and suite configuration from Excel files, enabling true data-driven testing.
- **PDFUtil**: Extracts text, page count, and metadata from PDF files for validation in download tests.
- **DBUtil**: Executes queries and validates results across MSSQL, Oracle, and DB2 databases.
- **StringUtil**: Advanced string formatting, random string generation, and regex utilities for dynamic test data.
- **DateUtil**: Flexible date and time generation and manipulation for temporal test scenarios.
- **XMLParserUtil**: Extracts values from XML using XPath, useful for SOAP API validation.
- **CLIUtil**: Parses command-line arguments for dynamic test suite execution.
- **Logger**: Centralized logging using Winston, with logs written to both console and file.
- **SuiteManager & SuiteTemplate**: Dynamically generates test suites based on Excel configuration, supporting parallel/serial/normal run modes.
- **Comprehensive Playwright Actions**: Custom wrappers for UI actions (alerts, checkboxes, dropdowns, edit boxes, etc.) and API actions (REST, SOAP, headers).
- **Allure & HTML Reporting**: Integrated reporting with screenshots, video on failure, and detailed logs.
- **Environment Control**: Easily switch browsers, environments, and test modes via `.env` and command-line arguments.

---

## **Features**

- Built-in libraries for UI, API (SOAP & REST), and DB (MSSQL, DB2, Oracle) automation.
- Supports execution in Chrome, Firefox, Edge, and WebKit browsers.
- Data-driven: Test data and execution control via Excel.
- Flexible run modes: Sequential, serial (fail-fast), and parallel.
- Utilities for file download, PDF reading, and more.
- Rich reporting: Playwright HTML, Allure, JUnit, and Monocart reports.
- Execution logs for traceability and debugging.
- Playwright UI Mode for interactive debugging.
- CI/CD ready (Jenkins, etc.).

---

## **Getting Started**

### 1. Installation

- Requires [Node.js](https://nodejs.org/) v14+
- Download or clone the repository:
  ```sh
  git clone https://github.com/VinayKumarBM/playwright-sample-project.git
  cd playwright-sample-project
  npm ci
  ```

### 2. Test Creation
- Create a test file with `.spec.ts` extension (e.g., `LoginTest.spec.ts`).
- In the Excel test data file, add a sheet named after your test (e.g., `LoginTest`).
- In the execution sheet, add a row for your new test and configure columns like run, mode, etc.

### 3. Execution
- To run a test suite:
  ```sh
  npm run create:suite SHEET=<SheetName> && npm test
  ```
- To run an individual test locally:
  ```sh
  set TEST_NAME=<TestFileName> && npm run local:test
  ```
- To run in [UI Mode](https://playwright.dev/docs/test-ui-mode):
  ```sh
  set TEST_NAME=<TestFileName> && npm run local:test:ui
  ```
- To change environment config at runtime (e.g., browser):
  ```sh
  set BROWSER=edge
  ```
- To generate Allure report:
  ```sh
  npm run report
  ```

### 4. Reports & Logs
- Playwright HTML report: `test-results/results/index.html`
- Execution log: `test-results/logs/execution.log`

---

## **Contributing & Feedback**

Feel free to open issues or submit pull requests for improvements. If you find this project helpful, please give it a Star ⭐ and Follow 👥!
