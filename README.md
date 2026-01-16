# Logic Tutor - CTAT Project

This is a CTAT (Cognitive Tutor Authoring Tools) project for teaching logic and rule-based reasoning.

This project was created for the **Adaptive Systems 2025-2026** course as part of the **Technology-Enhanced Adaptive Learning Practical Work**.

Group project members:
- Buonaccorsi Emanuele
- Osadici Darius
- Rădulescu Adelina

## Usage Instructions

### Opening in CTAT Authoring Tools

1. Place the LogicTutor folder in your CTAT workspace or any desired location
2. Launch **CTAT for HTML and Flash**
3. Select **File > Open Graph** and open the `LogicTutor/FinalBRDs/Problem1.brd` file (or `Problem2.brd`)
4. Select **File > Launch HTML Interface** and open the `LogicTutor/HTML/Problem1.html` file (or `Problem2.html`)
5. The tutor should load in your web browser


## Project Structure

```
LogicTutor/
├── HTML/
│   ├── Problem1.html          # Simple linear chain problem
│   ├── Problem2.html          # Complex branching problem
│   └── Assets/
│       ├── Problem1-styles.css
│       └── Problem2-styles.css
└── FinalBRDs/
    ├── Problem1.brd           # Behavior graph for Problem 1
    └── Problem2.brd           # Behavior graph for Problem 2
```

## Problems Overview

The tutors detect and provide feedback for:

1. **Firing a rule whose left-hand side is not true** - Students cannot fire a rule if its conditions aren't met
2. **Deducing a fact not in the right-hand side of the fired rule** - Students must correctly identify what each rule concludes

Both tutors provide hints at each step:
- General guidance about the current state
- More specific direction about which rule to consider
- Bottom-out hints with the exact answer


### Problem 1: Linear Rule Chain

**Rules:**
- R1: A → B
- R2: B → C
- R3: C → D

**Given:** A is true

**Task:** Students identify the sequence of rules fired and facts deduced.

**Solution:** R1 fires (deduces B) → R2 fires (deduces C) → R3 fires (deduces D)

This problem has a **single correct solution path**.

### Problem 2: Branching Rule Network

**Rules:**
- R1: A → B
- R2: A → C
- R3: C → D
- R4: B → E
- R5: E and D → F

**Given:** A is true

**Task:** Students identify the sequence of rules fired and facts deduced.

**Valid Solutions:** Multiple orderings are acceptable (e.g., R1→R4→R2→R3→R5 or R2→R1→R3→R4→R5, etc.)

This problem has **multiple valid solution paths** due to the branching nature of the rules. For this reason, a script was used to generate all possible correct sequences of rule firings.