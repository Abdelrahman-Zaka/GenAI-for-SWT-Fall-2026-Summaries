# 📘 Lecture 1: Software Testing Concepts & Basics

## 🎯 Concept Match (Reverse Dictionary)
*Read the description $\to$ Write the Term*

*   Disciplined process across SDLC to verify requirements, validate purpose, and identify defects $\to$ **Software Testing**
*   Testing executed manually without automation tools $\to$ **Manual Testing**
*   Testing executed by scripts or tools without human intervention $\to$ **Automated Testing**
*   Testing functionality with no knowledge of internal code structure $\to$ **Black Box Testing**
*   Testing with full knowledge of internal code and logic $\to$ **White Box Testing**
*   Testing with partial knowledge of internal structures $\to$ **Gray Box Testing**
*   Testing the smallest individual unit of code (function/method) $\to$ **Unit Testing**
*   Checking how modules/components interact together $\to$ **Integration Testing**
*   Validating the complete integrated system against specified requirements $\to$ **System Testing**
*   Ensuring the system meets end-user business needs and requirements $\to$ **Acceptance Testing (UAT)**
*   Sequential linear SDLC model where each phase must finish before the next begins $\to$ **Waterfall Model**
*   SDLC model developing software through repeated cycles and smaller increments $\to$ **Iterative Model**
*   SDLC model combining Waterfall structure with iterative loops focused on Risk Reduction $\to$ **Spiral Model**
*   Checking documents, design, and code ("Are we building the product right?") $\to$ **Verification**
*   Testing the actual running product ("Are we building the right product?") $\to$ **Validation**
*   Process-oriented QA approach focused on preventing defects $\to$ **Quality Assurance (QA)**
*   Product-oriented QC approach focused on identifying defects in deliverables $\to$ **Quality Control (QC)**
*   SDLC model where testing activities are planned in parallel with development phases $\to$ **V-Model**
*   Time-boxed development iterations in Agile (typically 1–4 weeks) $\to$ **Sprints**
*   Popular Agile framework using specific roles, events, and artifacts $\to$ **Scrum**
*   Early rough visual mock-up built to clarify requirements and gather feedback $\to$ **Prototype**
*   Combining features of two or more SDLC models to fit project needs $\to$ **Hybrid Model**
*   Moving testing activities earlier in the SDLC timeline $\to$ **Shift-Left Testing**

---

## 📋 Classifications & Lists

*   **Types of Testing (Execution Perspective):**
    *   Manual Testing (slower, high human involvement, best for exploratory/usability).
    *   Automated Testing (faster, low human involvement, best for regression/performance).

*   **Types of Testing (Knowledge Perspective):**
    *   Black Box, White Box, Gray Box.

*   **Levels of Testing (in order of scope):**
    1.  Unit Testing
    2.  Integration Testing
    3.  System Testing
    4.  Acceptance Testing (UAT)

*   **Common SDLC Models:**
    *   Waterfall, Iterative, Spiral, V-Model, Agile, Prototype, Hybrid, Derived.

*   **Spiral Model 4 Loop Steps:**
    1.  **Planning** (Define objectives/requirements).
    2.  **Risk Analysis** (Identify risks & build prototypes).
    3.  **Engineering** (Design, develop, and test).
    4.  **Evaluation** (Review with client & plan next loop).

*   **V-Model Phase Mapping (SDLC Verification $\leftrightarrow$ STLC Validation):**
    *   Requirement Analysis $\leftrightarrow$ Acceptance Testing
    *   System Design $\leftrightarrow$ System Testing
    *   Architecture Design $\leftrightarrow$ Integration Testing
    *   Module Design $\leftrightarrow$ Unit Testing

*   **Scrum Framework Key Components:**
    *   **Roles:** Product Owner, Scrum Master, Development Team.
    *   **Events:** Sprint, Sprint Planning, Daily Stand-up, Sprint Review, Sprint Retrospective.
    *   **Artifacts:** Product Backlog, Sprint Backlog, Increment.
    *   **Principles:** Transparency, Inspection, Adaptation.

---

## 🧠 Case Study Triggers (Decision Making)
*If the exam gives you a scenario $\to$ Identify the Solution/Concept*

*   **Scenario:** A project has well-defined, stable requirements with minimal expected changes, similar to 1970s defense projects.
    *   **Decision:** Waterfall Model
*   **Scenario:** You are building a complex banking app with high financial failure risks and need explicit customer risk evaluations per phase.
    *   **Decision:** Spiral Model
*   **Scenario:** You are building a mobile banking app prototype where buttons are clickable mock-ups without real money transfer capability.
    *   **Decision:** Prototype Model
*   **Scenario:** You need the formal initial planning structure of Waterfall combined with the short iterative development cycles of Agile.
    *   **Decision:** Hybrid Model
*   **Scenario:** You review the SRS document and architectural design for defects before any code is written.
    *   **Task:** Verification (Static Testing)
*   **Scenario:** You execute compiled unit test scripts and system test cases against Build 1.0.
    *   **Task:** Validation (Dynamic Testing)
*   **Scenario:** The developer implemented a login feature exactly as documented in the specification, but end users find it useless because it doesn't support SSO.
    *   **Diagnosis:** Verified but Not Valid (Misunderstood user need / incorrect requirements assumption).
*   **Scenario:** Instead of waiting for a completed build, QA testers review requirements and write test cases during the design phase.
    *   **Technique:** Shift-Left Testing

---

## ⚠️ Important Distinctions (Don't Mix These Up!)

*   **Verification vs. Validation:**
    *   *Verification:* Static testing (Inspections, Reviews, Walkthroughs) $\to$ "Did we build it according to specification?"
    *   *Validation:* Dynamic testing (Executing code) $\to$ "Does it actually solve the user's real need?"
*   **Waterfall Modern Reality:** Waterfall was originally designed for large aerospace/defense projects, but in modern tech it is considered too rigid for large systems and best suited only for small, stable projects.
*   **Agile Evolution:** Modern tech companies operate on **Agile + DevOps** (Sprints/Backlogs + CI/CD automated pipelines + AI-assisted QA).