# 📘 Lecture 2: Testing Life Cycle & Basics

## 🎯 Concept Match (Reverse Dictionary)
*Read the description $\to$ Write the Term*

### Part I: Testing Concepts & Lifecycle
*   Systematic sequence of testing phases executed during SDLC $\to$ **STLC (Software Testing Life Cycle)**
*   An internal software version delivered to QA for testing $\to$ **Build**
*   A stable software version deployed to production or target audience $\to$ **Release**
*   A human action or mistake during coding/design $\to$ **Error**
*   A flaw or fault in code resulting from a human error $\to$ **Defect / Bug**
*   An incorrect system behavior observed during execution $\to$ **Failure**
*   Quick broad check on a new build to decide if it is stable enough for deep testing $\to$ **Smoke Testing**
*   Testing system performance at expected maximum usage limit $\to$ **Load Testing**
*   Testing system beyond normal limits to find breaking points and recovery behavior $\to$ **Stress Testing**
*   Focused test on a bug fix/new feature checking logical behavior in surrounding areas $\to$ **Sanity Testing**
*   Re-executing exact failed test cases after a bug fix to confirm the bug is gone $\to$ **Retesting**
*   Testing existing features to ensure new code changes didn't break them $\to$ **Regression Testing**
*   Testing with valid inputs expecting successful execution $\to$ **Positive Testing**
*   Testing with invalid inputs expecting graceful error handling $\to$ **Negative Testing**
*   Simultaneous learning, test design, and test execution guided by a charter $\to$ **Exploratory Testing**
*   Unstructured, random testing without a plan or intention to learn system logic $\to$ **Ad-hoc Testing**
*   Unplanned, mindless random inputs (often automated) to check stability $\to$ **Monkey Testing**
*   Heavy brute-force testing directed repeatedly at one specific module $\to$ **Gorilla Testing**
*   High-level simple sentence describing what needs to be tested $\to$ **Test Scenario**
*   Formal blueprint documenting testing scope, strategy, schedule, and resources $\to$ **Test Plan**
*   Detailed step-by-step test instructions with preconditions and expected results $\to$ **Test Case**
*   Matrix mapping test cases directly to requirements $\to$ **RTM (Requirement Traceability Matrix)**

### Part II: System Testing & Coverage Criteria
*   Testing visual elements (layout, alignment, buttons) against specifications $\to$ **GUI Testing**
*   Rules or metrics used to determine if software has been sufficiently tested $\to$ **Coverage Criteria**
*   Coverage based on modeling code/system flow as nodes and edges $\to$ **Graph Coverage**
*   Coverage based on evaluating Boolean conditions to True and False $\to$ **Logic Coverage**
*   Coverage based on dividing input domain into equivalence groups $\to$ **Input Space Partitioning**
*   Coverage based on injecting small code changes (mutants) to test suite strength $\to$ **Mutation Testing**

---

## 📋 Classifications & Types

*   **STLC Phases (7 Steps):**
    1.  Requirement Analysis
    2.  Test Planning
    3.  Test Case Development
    4.  Test Environment Setup
    5.  Test Execution
    6.  Defect Reporting & Tracking
    7.  Test Cycle Closure

*   **Release Deployment Strategies:**
    *   Gradual / Staged Rollout
    *   A/B Testing

*   **The ISTQB Bug Chain:**
    `[ Human Action: ERROR ]` $\to$ `[ Code Flaw: DEFECT / BUG ]` $\to$ `[ Observed Behavior: FAILURE ]`

*   **Use Case Key Components:**
    *   Actor, Preconditions, Main Flow, Alternate Flow, Postconditions.

*   **Non-Functional System Testing Types:**
    *   **Performance:** Load, Stress, Endurance, Spike, Scalability.
    *   **Security:** Access control, vulnerability tests.
    *   **Usability:** User-friendliness and ease of use.
    *   **Compatibility:** Cross-browser, cross-OS, cross-device tests.

---

## 🧠 Case Study Triggers (Decision Making)
*If the exam gives you a scenario $\to$ Identify the Solution/Concept*

*   **Scenario:** In hardware engineering, powering on a new circuit to check if it literally emits smoke before detailed testing.
    *   **Origin Concept:** Smoke Testing
*   **Scenario:** Simulate 5,000 users logging in at once to verify response time stays under 3 seconds.
    *   **Type:** Load Testing
*   **Scenario:** Simulate 20,000+ users on a system designed for 5,000 to verify it crashes safely without data loss.
    *   **Type:** Stress Testing
*   **Scenario:** A developer fixes a login bug. You verify login with special characters (the bug) AND check if blank field validation still works logically.
    *   **Task:** Retesting (for fix) + Sanity Testing (for surrounding logic)
*   **Scenario:** After adding a new payment gateway, you test the item search and shopping cart to ensure they didn't break.
    *   **Task:** Regression Testing
*   **Scenario:** You test checkout by trying to delete cart items while payment is processing, or logging out during money transfer.
    *   **Type:** Exploratory Testing
*   **Scenario:** Pounding a single login page 1,000 times in a row with different credential combinations.
    *   **Type:** Gorilla Testing
*   **Scenario:** An automated script randomly generates garbage strings into every text box on a page.
    *   **Type:** Monkey Testing

---

## ⚠️ Important Distinctions (The "Don't Confuse" List)

1.  **Error vs. Bug vs. Failure:**
    *   *Error:* The human developer's mistake.
    *   *Bug/Defect:* The static flaw in the source code.
    *   *Failure:* The visible runtime error experienced during execution.
2.  **Retesting vs. Regression Testing:**
    *   *Retesting:* Narrow scope $\to$ repeating *failed* test cases to confirm a bug fix.
    *   *Regression:* Broad scope $\to$ checking *passing* test cases in unmodified modules to catch unintended side effects.
3.  **Smoke vs. Sanity Testing:**
    *   *Smoke:* Shallow & broad $\to$ verifies overall build stability.
    *   *Sanity:* Narrow & deep $\to$ verifies logical correctness of a specific fix/feature.
4.  **Monkey vs. Gorilla Testing:**
    *   *Monkey:* Random mindless clicks across the whole app.
    *   *Gorilla:* Repetitive brute-force testing focused on **one** module.