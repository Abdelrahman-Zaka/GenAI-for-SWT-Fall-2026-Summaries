# 📘 Lecture 3: Advanced Coverage Criteria & Input Space Partitioning

## 🎯 Concept Match (Reverse Dictionary)
*Read the description $\to$ Write the Term*

### Graph Coverage & Control Flow Graphs
*   A graph with exactly one initial node and one final node $\to$ **SESE Graph (Single-Entry, Single-Exit)**
*   A sequence of nodes starting at $N_0$ and ending at $N_f$ $\to$ **Test Path**
*   Criterion requiring every syntactically reachable node to be visited $\to$ **Node Coverage (NC)**
*   Criterion requiring every reachable path of length up to 1 to be visited $\to$ **Edge Coverage (EC)**
*   Criterion requiring every reachable path of length up to 2 to be visited $\to$ **Edge-Pair Coverage (EPC)**
*   A path where no node appears more than once (except possibly start and end node) $\to$ **Simple Path**
*   A simple path that is not a proper subpath of any other simple path $\to$ **Prime Path**
*   Criterion requiring test paths to tour every prime path in a graph $\to$ **Prime Path Coverage (PPC)**
*   Leaving a path and returning to the **exact same** node $\to$ **Sidetrip**
*   Leaving a path and returning to a **successor** node $\to$ **Detour**
*   A test requirement that cannot be satisfied due to dead code or logical contradiction $\to$ **Infeasible Test Requirement**
*   Strategy of satisfying test requirements without sidetrips first, then allowing sidetrips if needed $\to$ **Best Effort Touring**
*   A sequence of statements executed sequentially with no branching inside $\to$ **Basic Block**

### Data Flow Coverage
*   A location in code where a value is stored into memory $\to$ **Definition (def)**
*   A location in code where a variable's value is accessed $\to$ **Use**
*   A path from a def to a use where the variable is not re-defined $\to$ **Def-clear Path**
*   A pair $(l_i, l_j)$ where variable $v$ is defined at $l_i$ and used at $l_j$ $\to$ **DU Pair**
*   Data flow criterion requiring every def to reach at least **one** use $\to$ **All-defs Coverage (ADC)**
*   Data flow criterion requiring every def to reach **every** use $\to$ **All-uses Coverage (AUC)**
*   Data flow criterion requiring **all** def-clear paths between defs and uses to be toured $\to$ **All-du-paths Coverage (ADUPC)**

### Input Space Partitioning (ISP)
*   Property where input blocks have no common elements ($b_i \cap b_j = \emptyset$) $\to$ **Pairwise Disjoint**
*   Property where input blocks together cover the entire domain ($\bigcup b_i = D$) $\to$ **Complete Partition**
*   ISP criterion testing every possible combination of blocks across characteristics $\to$ **All Combinations Coverage (ACoC)**
*   ISP criterion selecting at least one value from each block of each characteristic $\to$ **Each Choice Coverage (EC)**
*   ISP criterion pairing every block of each characteristic with every block of other characteristics $\to$ **Pair-Wise Coverage (PW)**
*   ISP criterion selecting base choices for parameters and varying one parameter at a time $\to$ **Base Choice Coverage (BC)**

---

## 📋 Classifications & Formulas

*   **Structural Graph Criteria Hierarchy:**
    Node Coverage $\subset$ Edge Coverage $\subset$ Edge-Pair Coverage $\subset$ Prime Path Coverage.
    *(Note: Complete Path Coverage is impossible if loops exist).*

*   **Data Flow Hierarchy:**
    All-defs Coverage $\subset$ All-uses Coverage $\subset$ All-du-paths Coverage.

*   **ISP Criteria Test Count Formulas:**
    *   **All Combinations (ACoC):** $\prod_{i=1}^Q B_i$
    *   **Each Choice (EC):** $\max_{i=1}^Q (B_i)$
    *   **Pair-Wise (PW):** $\ge (\text{largest } B_i) \times (\text{second largest } B_j)$
    *   **Base Choice (BC):** $1 + \sum_{i=1}^Q (B_i - 1)$

*   **Steps to Find Prime Paths:**
    1.  List length 0 paths (all individual nodes).
    2.  Extend paths by outgoing edges (length 1, 2, ...).
    3.  Stop extending when path revisits a node (mark `*` for cycle) or hits a dead end (mark `!` for terminal).
    4.  Cross out any path that is a subpath of a longer valid path. Remaining `!` and `*` paths are Prime Paths.

*   **Theoretical vs. Modern Practical Coverage Terms:**
    *   Node Coverage $\leftrightarrow$ **Statement Coverage**
    *   Edge Coverage $\leftrightarrow$ **Branch Coverage**
    *   Complete Path Coverage $\leftrightarrow$ **Path Coverage**
    *   Data Flow Coverage $\leftrightarrow$ **Def-Use Coverage**

---

## 🧠 Case Study Triggers (Decision Making)
*If the exam gives you a scenario $\to$ Identify the Solution/Concept*

*   **Scenario:** A graph contains a self-loop edge on node $n$. Edge-Pair Coverage requires $[n,n,m]$, but Prime Path Coverage does not require it because $[n,n,m]$ is not a simple path.
    *   **Fact:** PPC does **NOT** subsume EPC.
*   **Scenario:** You test a path $X > 0$ and $X < 0$ in code, which can never be executed in real runs.
    *   **Diagnosis:** Infeasible Test Requirement
*   **Scenario:** You defined partitions for file sorting, but a file of length 1 fits into both "Ascending" and "Descending" blocks.
    *   **Problem:** Partition is not **Disjoint**.
*   **Scenario:** You defined age partitions as $<18$ and $>18$, but age 18 fits nowhere.
    *   **Problem:** Partition is not **Complete**.
*   **Scenario:** You have a function with 3 integer inputs, each having 3 partitions (Negative, Zero, Positive). You want to run base choice testing with baseline `(0,0,0)`.
    *   **Number of Tests:** $1 + (3-1) + (3-1) + (3-1) = 7$ tests.
*   **Scenario:** In the same scenario above, you decide to test All Combinations (ACoC).
    *   **Number of Tests:** $3 \times 3 \times 3 = 27$ tests.

---

## ⚠️ Important Distinctions

*   **Sidetrip vs. Detour:**
    *   *Sidetrip:* Path leaves the subpath and returns to the **same node** $n_i$.
    *   *Detour:* Path leaves the subpath at $n_i$ and returns to a **successor node** $n_j$.
*   **Def vs. Use in Source Code:**
    *   `def`: Left side of assignment (`x = 5`), actual output parameter, formal method parameter, input read.
    *   `use`: Right side of assignment (`y = x`), conditional test (`if (x > 0)`), actual input parameter, return statement.
*   **Equivalence Partitioning (EP) vs. Boundary Value Analysis (BVA):**
    *   *EP:* Selects representative values from inside each block.
    *   *BVA:* Selects values at the edges/boundaries (just below, at, and just above boundaries) where defects naturally concentrate.