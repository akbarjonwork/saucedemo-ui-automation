# 🧾 UI Automation Test Plan
**Project:** SauceDemo – Web UI Automation  
**Author:** Akbarjon Olimov  
**Version:** 1.0  
**Date:** October 2025  

---

## 1. Introduction
This document outlines the scope, objectives, strategy, and deliverables for the **UI Automation Testing of SauceDemo (v1)** — a sample e-commerce web application designed for QA and automation practice.  

The project aims to create a **complete, modular, and CI-integrated Playwright automation framework** that validates key user workflows such as login, product browsing, cart management, checkout, and logout.

The automation will serve as part of a professional **QA portfolio**, demonstrating best practices in framework design, reporting, and documentation.

---

## 2. Objectives
- Build a robust UI automation framework using **Python, Playwright, and Pytest**.  
- Validate core user journeys across **Login → Purchase → Logout**.  
- Implement **Page Object Model (POM)** for scalable and readable test maintenance.  
- Integrate **Allure & Pytest-HTML** for clear reporting.  
- Automate execution through **GitHub Actions CI/CD**.  
- Provide professional **QA documentation** (plan, strategy, and reports).

---

## 3. Scope

### In Scope
Automation coverage includes the following SauceDemo features:
- **Login Page:** Valid, invalid, and locked user login scenarios  
- **Inventory Page:** Product listing validation, sorting, add/remove cart actions  
- **Cart Page:** Item count verification, item removal  
- **Checkout Page:** Entering user information, verifying total amount, order completion  
- **Logout Functionality:** Session cleanup and redirection validation  
- Execution across **Chrome and Firefox** browsers  
- **Test categorization:** `@smoke`, `@regression`, `@sanity`

### Out of Scope
- Backend or database validations  
- API testing  
- Mobile and responsive UI testing  
- Performance, accessibility, or security testing  

---

## 4. Test Approach

| Aspect | Approach |
|--------|-----------|
| **Framework** | Playwright + Pytest |
| **Design Pattern** | Page Object Model (POM) |
| **Execution Environment** | Local + GitHub Actions |
| **Test Data** | External JSON file (`data/test_data.json`) |
| **Environment Variables** | `.env` for credentials and base URL |
| **Test Categorization** | Pytest markers: smoke, regression, sanity |
| **Reporting** | Allure + pytest-html |
| **Assertions** | `expect()` assertions for URL, text, and element visibility |
| **Wait Strategy** | Default Playwright waits, explicit waits for dynamic elements |
| **Locators** | Prefer `data-test` attributes, fallback to stable CSS/XPath |

---

## 5. Test Environment

| Component | Description |
|------------|-------------|
| **Application URL** | [https://www.saucedemo.com/v1/](https://www.saucedemo.com/v1/) |
| **Browsers** | Chrome (latest), Firefox (latest) |
| **OS Platforms** | Windows 10+, Ubuntu 22.04 |
| **Python Version** | 3.11+ |
| **Dependencies** | playwright, pytest, pytest-html, allure-pytest, python-dotenv |
| **CI/CD** | GitHub Actions workflow for automated test runs |

---

## 6. Test Deliverables
- Source code in public GitHub repo  
- Automated test scripts for key flows (10–15 tests total)  
- HTML & Allure reports with screenshots  
- Logs of failed test runs  
- `Docs/` folder containing:
  - Test Plan  
  - Test Strategy  
  - Test Summary Report  
  - Sample Bug Report  
- CI/CD pipeline YAML file (`.github/workflows/ci.yml`)  
- `README.md` with project overview and badges  

---

## 7. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| **QA Automation Engineer (Akbarjon Olimov)** | Develop, execute, and maintain test scripts |
| **Reviewer (Optional)** | Review test structure, suggest optimizations |
| **DevOps (Optional)** | Maintain CI/CD pipeline setup |
| **Project Owner (Portfolio)** | Maintain documentation and public repository |

---

## 8. Test Schedule & Milestones

| Phase | Duration | Deliverables |
|--------|-----------|--------------|
| Framework Setup | 2 days | Folder structure, config, environment setup |
| POM Implementation | 3 days | Pages for login, inventory, cart, checkout |
| Test Case Development | 5 days | CRUD & E2E flows implemented |
| Data-Driven Enhancements | 3 days | JSON-based data, parametrized tests |
| Reporting + CI/CD | 3 days | GitHub Actions + Allure setup |
| Documentation | 2 days | Docs & screenshots added |
| Finalization | 2 days | Review, run tests, cleanup |

---

## 9. Risks & Mitigation

| Risk | Impact | Mitigation |
|------|---------|------------|
| Locator changes in demo site | Medium | Use robust `data-test` attributes |
| Test flakiness | Medium | Use built-in Playwright waits and retries |
| CI/CD job failure | Medium | Add retry + debug step in workflow |
| Report generation error | Low | Validate Allure configuration locally |
| Internet dependency (demo site) | Medium | Run tests only when site is stable |

---

## 10. Entry & Exit Criteria

**Entry Criteria**
- Application under test is available and stable  
- Framework setup completed  
- Environment variables configured  

**Exit Criteria**
- All high-priority smoke and regression tests executed  
- No critical or blocker failures open  
- Final reports generated and reviewed  

---

## 11. Reporting
- **Allure Report:** Comprehensive execution history with screenshots  
- **pytest-html:** Quick HTML summary after local runs  
- **GitHub Actions Logs:** CI run results visible in Actions tab  
- **Summary Report:** Shared in `/Docs/Test_Summary_Report.md`

---

## 12. References
- [SauceDemo Web App](https://www.saucedemo.com/v1/)  
- [Playwright Python Docs](https://playwright.dev/python)  
- [Pytest Docs](https://docs.pytest.org/)  
- [Allure Framework](https://docs.qameta.io/allure/)  

---

 **Outcome:**  
This Test Plan defines the entire scope, approach, and execution plan for the UI automation of **SauceDemo v1**, serving as both a **learning and professional showcase project**. It can be included directly as `Docs/Test_Plan.md` in your GitHub repository.
