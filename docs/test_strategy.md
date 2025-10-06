# Test Strategy – SauceDemo UI Automation Project

## 1. Introduction

This Test Strategy document defines the overall approach, standards, tools, and processes to be followed for automating UI tests of the **SauceDemo Web Application** (https://www.saucedemo.com/v1/).  
The purpose of this strategy is to ensure consistent, maintainable, and scalable UI automation practices using **Playwright + Pytest**.

---

## 2. Objectives

- Define a unified framework for UI automation.
- Establish standards for test structure, naming, and reporting.
- Ensure early defect detection through reliable regression automation.
- Enable continuous testing using CI/CD integration.
- Deliver high-quality test reports and documentation for stakeholders.

---

## 3. Scope

### In Scope
- UI functional and end-to-end testing of the SauceDemo application.
- Test automation for core workflows (Login, Products, Cart, Checkout, Logout).
- Cross-browser testing on Chromium, Firefox, and WebKit.
- Smoke and regression test suites.

### Out of Scope
- API and backend testing.
- Load/performance testing.
- Mobile app automation (not covered in this phase).

---

## 4. Test Approach

The testing approach will follow **data-driven** and **modular** principles using **Page Object Model (POM)** for maintainability.

### Framework Stack
| Component | Tool |
|------------|------|
| Language | Python |
| Framework | Playwright + Pytest |
| Reporting | Allure / Pytest-HTML |
| CI/CD | GitHub Actions |
| Version Control | Git + GitHub |
| Configuration | dotenv / config.py |

---

## 5. Test Levels

| Level | Description |
|--------|--------------|
| **Smoke Tests** | Verify basic functionality and system stability. |
| **Regression Tests** | Validate key workflows after changes or deployments. |
| **E2E Tests** | Cover user journeys like login → add to cart → checkout. |

Each test case will be tagged using `@pytest.mark` to separate suites.

---

## 6. Test Data Management

- Static test data will be stored in JSON or `.env` files.
- Sensitive information (e.g., credentials) will be stored in `.env`.
- Dynamic data generation handled through helper functions in `utils/helpers.py`.

---

## 7. Test Environment

| Environment | URL | Description |
|--------------|-----|--------------|
| **QA/Stage** | https://www.saucedemo.com/v1/ | Public testing environment used for automation validation. |

The Playwright configuration will handle environment variables using `.env` and base URLs defined in `config.py`.

---

## 8. Test Execution & Scheduling

### Local Execution
Developers or QA engineers will run tests locally during development using:
```bash
pytest --alluredir=allure-results
allure serve allure-results
