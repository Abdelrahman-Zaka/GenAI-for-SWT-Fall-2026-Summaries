# CMPS457: Generative AI for SW Testing - Comprehensive Question Bank

**Instructions:**
*   This document contains **Practice Exam A** and **Practice Exam B**. 
*   Both exams strictly follow your professor's format (23 short-answer, 2 medium-answer, 1 applied question).
*   Both exams follow the strict weight distribution: ~1/3 Generative AI concepts and ~2/3 Software Testing concepts.
*   **No lecture headers are included.** You must rely on your conceptual understanding to identify the topic.
*   The answer keys for both exams are located at the bottom of this document.

---

## 📝 PRACTICE EXAM A

### Section 1: Short-Answer Questions (23 Questions)

1. You pass a Jira bug log containing untrusted user text to an LLM for summarization. What prompt engineering tactic should you use to prevent the user text from executing a prompt injection attack?
2. You ask a Base-LLM to "Generate 3 unit test cases for the login page." Instead of doing this, it outputs "4. Generate unit test cases for the checkout page." Why did it behave this way?
3. When configuring an LLM API for an automated script where you need identical, predictable test data generated every single time, what specific parameter setting should you use?
4. In a multi-turn LLM chat architecture, which specific message role is used to define the assistant's overall persona and strict operational boundaries?
5. A tester blindly approves an AI-generated test script without reviewing it because they assume the AI is smarter than them. What psychological concept describes this phenomenon?
6. You are crafting a prompt and include two examples of valid JSON input and output before asking the model to process your actual data. What is this prompting technique called?
7. According to the Ng & Fulford framework, if you instruct an LLM to "Review your own answer and ensure you covered boundary cases before returning the final output," which core prompt engineering principle are you applying?
8. What is the name of the evaluation method where you use a secondary, highly capable LLM to grade or assess the output of a primary LLM based on predefined criteria?
9. You are managing a large, complex, and highly critical banking software project where mitigating financial failure is the top priority. Which SDLC model explicitly focuses on risk analysis at every cycle?
10. A QA team is reviewing the Software Requirements Specification (SRS) document to ensure the logic makes sense before any code is written. Does this activity represent Verification or Validation?
11. In the V-Model, which specific dynamic testing phase (on the right side of the V) corresponds to verifying the System Design phase (on the left side of the V)?
12. A QA engineer decides to start writing test cases and reviewing database architecture during the Design phase rather than waiting for the developers to finish coding. What is this proactive approach called?
13. A developer patches a specific bug in the checkout cart. The tester verifies the cart works, but then intentionally runs passing test cases on the user profile page to ensure the new code didn't break old features. What type of testing is performed on the profile page?
14. According to the ISTQB chain, a human developer makes an **Error** which creates a **Defect** in the code. What is the term for the incorrect behavior observed by the end-user when that code is executed?
15. A tester pounds a single login module repetitively with brute-force inputs for an hour to see how that specific module handles the strain. What type of testing is this?
16. During which phase of the Software Testing Life Cycle (STLC) does the QA team provision the hardware, install the necessary software, and create the mock test accounts needed to run the tests?
17. In Graph Coverage, what is the specific term for a path where no node appears more than once, except possibly the first and last nodes?
18. In Input Space Partitioning (ISP), if you create partitions for "Age" as `< 18` and `> 18`, but a user inputs `18` and the system has no block for it, which fundamental property of partitioning have you violated?
19. In Data Flow Coverage, what do we call a path between the assignment of a variable (def) and its usage (use) where the variable is *never* reassigned?
20. Your team has 100 different valid and invalid username/password combinations to test. Instead of writing 100 test scripts, you write 1 generic script that loops through an Excel file. Which automation framework are you using?
21. What test automation metric is calculated by dividing the number of defects found in production by the total number of defects found in both QA and production?
22. Your team wants non-technical product managers to be able to write automated tests using human-readable `Given-When-Then` syntax. Which framework allows for this?
23. In test automation ROI, the "Break-Even Condition" states that automation is only viable if the manual effort saved per run is strictly greater than what other metric?

### Section 2: Medium-Answer Questions (2 Questions)

24. A test manager wants to automate 100% of the UI tests for an application that undergoes massive visual layout changes every three days. Briefly explain why this is a bad idea regarding Return on Investment (ROI), and state how the future of AI testing (specifically regarding locators) might attempt to solve this.

25. While using an LLM to generate integration test scripts, the model confidently references a testing library and API endpoint that do not actually exist. Identify this specific LLM limitation and provide one prompt engineering tactic you can use to mitigate it.

### Section 3: Applied Coverage Criteria Question (1 Question)

26. **Code Analysis & Coverage:**
Read the following Python code snippet carefully.

```python
1. def calculate_fee(weight, is_express):
2.     fee = 10                       
3.     if weight > 20:                
4.         fee = 50                   
5.     if is_express:                 
6.         fee = fee + 20             
7.     return fee                     
```

*   **Task A (CFG):** List the nodes (by line number) and the edges to represent the Control Flow Graph.
*   **Task B (Graph Coverage):** List the Test Requirements (TR) necessary to achieve **Edge Coverage (EC)**.
*   **Task C (Data Flow):** Identify all the nodes where the variable `fee` is **defined (def)** and all the nodes where `fee` is **used (use)**.
*   **Task D (Data Flow):** Provide one valid **DU-Path** for the variable `fee` starting from the definition at Node 4 to a use at Node 6.
*   **Task E (Input Space Partitioning):** Using Boundary Value Analysis (BVA), what specific integer test values should you choose for the `weight` parameter around the condition in line 3?

---

## 📝 PRACTICE EXAM B

### Section 1: Short-Answer Questions (23 Questions)

1. What specific LLM capability is being utilized when you prompt the model to convert a manual English test case into a Python Selenium script?
2. If an LLM generates a mathematically impossible output or cites a fake source but sounds highly confident, what is this occurrence called?
3. What is the process of testing, analyzing errors, and refining the instructions sent to an AI in a step-by-step loop called?
4. When maintaining a chatbot conversation, why must the entire conversation history (previous user and assistant messages) be sent back to the API with every new prompt?
5. You want an LLM to generate diverse, out-of-the-box exploratory testing ideas. Should the model temperature be set closer to `0` or `1`?
6. When comparing an LLM's response quality against a predefined expected answer using metrics like "Accuracy" or "Recall", are you using an Objective Metric or a Subjective Metric?
7. According to the Ng & Fulford framework, explicitly asking the LLM to output its answer in JSON format falls under which core principle?
8. What is the specific training technique that uses human ratings to align an LLM so that it is helpful, honest, and harmless?
9. Which SDLC model is strictly sequential, has no phase overlap, and is generally considered too rigid and inflexible for large, modern software systems?
10. Does Quality Control (QC) represent a *preventive* approach focused on improving the process, or a *corrective* approach focused on finding bugs in the product?
11. What type of testing ensures that individual, smaller units of code function properly in isolation before they are combined?
12. You receive a new build and perform a quick, shallow check to ensure the application simply starts up and the login screen loads. What is this type of testing called?
13. A tester performs unscripted, random clicks on a UI without any goal, plan, or intention of learning the system's logic. What is this testing called?
14. What is the formal document that acts as a blueprint, outlining the scope, strategy, schedule, and resources of testing?
15. What type of graph coverage requires test paths to tour every simple path that is not a proper subpath of any other simple path?
16. In graph coverage, what is it called when a test path leaves the required subpath and returns to the *exact same* node?
17. A test requirement dictates that a test path must simultaneously satisfy `x < 0` and `x > 10`. What is this type of requirement called?
18. Which data flow coverage criterion requires covering every def-clear path from a definition to *all* of its possible uses?
19. Which Input Space Partitioning (ISP) combinatorial criterion pairs every block of a characteristic with every block of all other characteristics?
20. Which automation framework abstracts test actions into human-readable tables (e.g., `EnterText`, `ClickButton`) that are read by an underlying execution engine?
21. What is the term for the percentage of automated tests that yield inconsistent results (sometimes passing, sometimes failing) on identical code builds?
22. Viewing an application under test as a Finite State Machine ($S_{start} \to Action \to S_{next}$) is known as what view of automated testing?
23. Which Agile artifact holds the specific list of features and tasks selected to be developed in the current 1-4 week iteration?

### Section 2: Medium-Answer Questions (2 Questions)

24. A QA team is using a Base Choice Coverage strategy for an e-commerce checkout featuring 5 input variables. How does a Hybrid framework (combining Modular/POM and Data-Driven) make executing these test variations highly efficient for the team?

25. Explain why passing a "System Message" with strict boundaries is crucial when building an LLM-assisted test case generator, and provide one example of what that message might contain.

### Section 3: Applied Coverage Criteria Question (1 Question)

26. **Code Analysis & Coverage:**
Read the following Python code snippet carefully.

```python
1. def check_status(age, score):
2.     status = "Pending"
3.     if age < 18:
4.         status = "Minor"
5.     if score > 80:
6.         status = "Honors"
7.     return status
```

*   **Task A (CFG):** List the nodes (by line number) and the edges to represent the Control Flow Graph.
*   **Task B (Logic Coverage):** Identify the two predicates in this code. What specific test values for `age` and `score` would you use to achieve full Predicate Coverage?
*   **Task C (Data Flow):** Identify all the nodes where the variable `status` is **defined (def)** and all the nodes where it is **used (use)**.
*   **Task D (Data Flow):** Provide one valid **DU-Path** for the variable `status` starting from the definition at Node 2 to the use at Node 7.
*   **Task E (Input Space Partitioning):** Using Equivalence Partitioning (NOT Boundary Value Analysis) for the `score` parameter based strictly on line 5, what are the two logical partition blocks?

---
<br><br>

# 🗝️ ANSWER KEYS (For Self-Study)

## EXAM A - Answer Key

**Section 1:**
1. Use Delimiters (e.g., `<bug_log>...</bug_log>`).
2. A Base-LLM predicts the next most likely text token based on raw data; it has not been Instruction-Tuned via RLHF to follow commands.
3. Model Temperature = 0.
4. The System Message (or System Role).
5. Cognitive Bias (specifically Automation Bias / Overtrust).
6. Few-Shot Prompting.
7. Principle 2: Give the model time to think.
8. LLM-as-a-Judge.
9. Spiral Model.
10. Verification (checking documents/processes, "Am I building it right?").
11. System Testing.
12. Shift-Left Testing.
13. Regression Testing.
14. Failure.
15. Gorilla Testing.
16. Test Environment Setup.
17. Simple Path.
18. Completeness (The partitions do not cover the entire domain).
19. Def-clear path.
20. Data-Driven Framework.
21. Defect Leakage Rate.
22. BDD (Behavior Driven Development).
23. The maintenance effort (or cost) per execution run.

**Section 2:**
24. Automating a highly volatile UI is a bad idea because the maintenance effort per run will exceed the manual effort saved, making a positive ROI mathematically impossible. However, the future of AI testing introduces "Self-Healing Tests," which use AI to automatically detect and repair broken element locators at runtime.
25. This limitation is called a Hallucination. You can mitigate this by covering assumptions in your prompt (e.g., "Only use standard libraries; if a feature is not native, state 'Cannot be done'") or by instructing the model to review its own solution against official documentation before outputting the code.

**Section 3:**
*   **Task A (CFG):** Nodes: `2, 3, 4, 5, 6, 7`. Edges: `(2,3), (3,4), (3,5), (4,5), (5,6), (5,7), (6,7)`.
*   **Task B (Edge Coverage):** TRs: `(2,3), (3,4), (3,5), (4,5), (5,6), (5,7), (6,7)`. *(A test suite like `[2,3,4,5,6,7]` and `[2,3,5,7]` satisfies this).*
*   **Task C (Data Flow - fee):** Defs: `2, 4, 6`. Uses: `6, 7`.
*   **Task D (DU-Path):** Path: `[4, 5, 6]`. *(The def at 4 reaches the use at 6 without being redefined).*
*   **Task E (ISP - BVA):** Test values: `19, 20, 21`. *(Testing just below, exactly at, and just above the `> 20` boundary).*

---

## EXAM B - Answer Key

**Section 1:**
1. Translating & Transforming.
2. Hallucination.
3. Iterative Prompting.
4. LLMs are stateless; providing the history is required to maintain conversational context in a single-turn API structure.
5. Closer to 1 (High temperature increases randomness and creativity).
6. Objective Metric.
7. Principle 1: Write clear and specific instructions (Tactic: Ask for structured output).
8. RLHF (Reinforcement Learning from Human Feedback).
9. Waterfall Model.
10. Corrective (Product-oriented to find bugs).
11. Unit Testing.
12. Smoke Testing.
13. Ad-hoc Testing.
14. Test Plan.
15. Prime Path Coverage (PPC).
16. Sidetrip.
17. Infeasible Test Requirement.
18. All-uses Coverage (AUC).
19. Pair-Wise Coverage (PW).
20. Keyword-Driven Framework.
21. Flaky Tests Rate.
22. Engineering View.
23. Sprint Backlog.

**Section 2:**
24. A hybrid framework allows the team to keep the UI interaction logic highly reusable (Modular/POM), while the Data-Driven aspect allows a *single* automation script to loop through an external Excel file containing all the Base Choice input combinations, minimizing code duplication.
25. A System Message provides strict rules and context to prevent the LLM from generating irrelevant or conversational outputs. Example: "You are an automated QA bot. You must only output valid JSON test cases and never output conversational text."

**Section 3:**
*   **Task A (CFG):** Nodes: `2, 3, 4, 5, 6, 7`. Edges: `(2,3), (3,4), (3,5), (4,5), (5,6), (5,7), (6,7)`.
*   **Task B (Logic Coverage):** Predicates: `(age < 18)` and `(score > 80)`. To achieve Predicate Coverage (making each True and False), use test values like: Test 1 (`age=10`, `score=90` $\to$ both True) and Test 2 (`age=20`, `score=50` $\to$ both False).
*   **Task C (Data Flow - status):** Defs: `2, 4, 6`. Uses: `7`.
*   **Task D (DU-Path):** Path: `[2, 3, 5, 7]`. *(The base def at 2 reaches the return at 7 because the `if` conditions were bypassed).*
*   **Task E (ISP - EP):** Block 1: `score <= 80`. Block 2: `score > 80`.