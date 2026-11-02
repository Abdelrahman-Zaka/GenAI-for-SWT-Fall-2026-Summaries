# 📘 Lecture 4: Automated Testing Architecture & Design

## 🎯 Concept Match (Reverse Dictionary)
*Read the description $\to$ Write the Term*

*   Executing pre-scripted tests using software to compare actual vs. expected outcomes $\to$ **Automated Testing**
*   Modeling Application Under Test as $S = (Q, \Sigma, \delta, q_0, F)$ $\to$ **Engineering View of Automation**
*   Challenge of guaranteeing a deterministic initial state $q_0$ across async/browser boundaries $\to$ **State Reset Challenge**
*   Preventing shared database mutations from coupling inter-test dependencies $\to$ **Side-Effect Isolation**
*   Rapid changes in UI elements/APIs exponentially increasing script maintenance $\to$ **Interface Volatility**
*   Tests randomly passing or failing on identical code due to async timing or network delays $\to$ **Flakiness**
*   Architectural blueprint defining organization of test code, assets, and processes $\to$ **Test Automation Framework**
*   Record-and-playback framework with sequential hard-coded steps and data $\to$ **Linear Framework**
*   Framework separating UI interaction logic (Pages) from Test Execution flows $\to$ **Modular Framework (POM)**
*   Framework separating test logic steps from external test input files (CSV/Excel) $\to$ **Data-Driven Framework**
*   Framework abstracting actions into human-readable keywords (e.g. `ClickButton`) $\to$ **Keyword-Driven Framework**
*   Framework using Gherkin syntax (`Given-When-Then`) to bridge business and QA $\to$ **BDD (Behavior Driven Development)**
*   Combining Modular (POM) structure with Data-Driven inputs and Keywords $\to$ **Hybrid Framework**
*   Percentage of total manual test cases converted into automated scripts $\to$ **Automation Coverage**
*   Percentage of automated tests showing inconsistent results on identical builds $\to$ **Flaky Tests Rate**
*   Percentage of defects that escape QA automation and are caught in production $\to$ **Defect Leakage Rate**
*   Average time elapsed from code commit until an automated build failure is alerted $\to$ **Mean Time to Detect (MTTD)**
*   Financial metric calculated as `(Manual Effort Saved - Automation Cost) / Automation Cost` $\to$ **Return on Investment (ROI)**
*   Feature where AI automatically repairs broken element locators at runtime $\to$ **Self-Healing Testing**

---

## 📋 Classifications & Formulas

*   **Automation Framework Types:**
    1.  Linear (Record & Playback)
    2.  Modular (Page Object Model - POM)
    3.  Data-Driven
    4.  Keyword-Driven
    5.  BDD (Behavior Driven Development)
    6.  Hybrid

*   **Relative Effort of Modification Across Frameworks:**
    | Framework | Interface / Locators | Test Sequence | Test Data |
    | :--- | :--- | :--- | :--- |
    | **Linear** | High 🔴 | High 🔴 | High 🔴 |
    | **Modular (POM)** | Low 🟢 | Medium 🟡 | Medium 🟡 |
    | **Data-Driven** | Medium 🟡 | Medium 🟡 | Low 🟢 |
    | **Keyword-Driven** | Medium 🟡 | Low 🟢 | Low 🟢 |
    | **BDD** | Low 🟢 | Medium 🟡 | Medium 🟡 |
    | **Hybrid** | Low 🟢 | Low 🟢 | Low 🟢 |

*   **ROI & Break-Even Formulas:**
    *   $$ROI = \frac{\text{Manual Effort Saved} - \text{Automation Cost}}{\text{Automation Cost}}$$
    *   **Break-Even Threshold Condition:**
        $$N > \frac{\text{Automation Cost}}{\text{Manual Effort Saved per run} - \text{Maintenance Effort per run}}$$

*   **Critical ROI Boundary Conditions:**
    *   **High Volatility Limit:** If Maintenance effort per run $\ge$ Manual Effort Saved per run, break-even is **mathematically impossible** regardless of run count $N$.
    *   **High Frequency Scale ($N > 1000$):** In continuous deployment pipelines, per-execution marginal cost approaches zero, maximizing ROI.

---

## 🧠 Case Study Triggers (Decision Making)

*   **Scenario:** You need to test a login feature against 100 different invalid username and password pairs stored in an Excel sheet.
    *   **Decision:** Data-Driven Framework
*   **Scenario:** You want non-technical Business Analysts to write test steps in spreadsheets using actions like `TypeInField` and `ClickButton`.
    *   **Decision:** Keyword-Driven Framework
*   **Scenario:** Business stakeholders, developers, and QA want a single readable source of truth written in `Given-When-Then` format.
    *   **Decision:** BDD Framework (Gherkin)
*   **Scenario:** A UI button locator changes on the web page, but you only want to update the locator in ONE single file without breaking 50 test scripts.
    *   **Decision:** Modular Framework (Page Object Model)
*   **Scenario:** A manual test takes 40 hours per run. Building automation costs 160 hours, maintenance is 5 hours/run, and you run it 24 times a year.
    *   **Calculation:** Saved = $40 \times 24 = 960$ hrs. Cost = $160 + (5 \times 24) = 280$ hrs. $ROI = \frac{960 - 280}{280} = 2.43$ (243% return).
*   **Scenario:** A feature's UI changes completely every single day, requiring 10 hours of script repair for every 2 hours of manual testing saved.
    *   **Diagnosis:** High Volatility Limit (Do NOT Automate).

---

## ⚠️ Important Distinctions

*   **When to Automate:** Regression testing, performance/load tests, data-driven tests, stable core features, cross-browser suites, CI/CD smoke pipelines.
*   **When NOT to Automate:** Exploratory testing, user experience (UX) usability tests, unstable/rapidly changing features, complex one-time scenarios.
*   **Linear vs. Modular (POM):** Linear puts locators, steps, and data in one file (hard to maintain). Modular separates locator pages from test scripts (easy to maintain).