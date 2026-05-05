# Worksheet: Propositional Logic & First-Order Logic
**Foundations of Artificial Intelligence – SS 2026**
*University of Bremen, Institute for Artificial Intelligence*

---

> **Instructions:** Written tasks (✏️) should be answered directly in this document or in a Markdown cell in the notebook. Programming tasks (🐍) belong in `logic_exercises.ipynb`. Estimated time: **~60 minutes**.

---

## Part 1 – Propositional Logic: Entailment & Satisfiability ✏️ *(~10 min)*

**1.1** Is the following entailment true or false? Justify your answer.

$$A \models A \lor B$$

> True, because if $A$ then also $A \lor B$ (only one needs to be true).

**1.2** Is the formula $(A \to B) \lor (B \to A)$ a tautology? Prove your answer using a truth table.

> The formula is a tautology, i.e. it is always true.

| $A$ | $B$ | $A \to B$ | $B \to A$ | $(A \to B) \lor (B \to A)$ |
|-----|-----|-----------|-----------|----------------------------|
|  F  |  F  |     T     |     T     |             T              |
|  F  |  T  |     T     |     F     |             T              |
|  T  |  F  |     F     |     T     |             T              |
|  T  |  T  |     T     |     T     |             T              |

**1.3** For each formula below, state whether it is **satisfiable**, **unsatisfiable**, or a **tautology**:

| # | Formula | Satisfiable? | Unsatisfiable? | Tautology? |
|---|---------|-------------|---------------|-----------|
| i | $A \land \lnot A$ | | X | |
| ii | $A \lor \lnot A$ | | | X |
| iii | $(A \to B) \land (B \to A)$ | X | | |
| iv | $\lnot(A \lor B) \land A$ | | X | |

**1.4** Does $A \leftrightarrow B$ entail $A \to B$? Explain why.

> It does. $A \leftrightarrow B \equiv (A \to B) \land (B \to A)$.

**1.5** Which of the following can be entailed from $A \land B$?

- (a) $A \lor B \lor C$
- (b) $A \leftrightarrow B$
- (c) None of the above

> ~~(c)~~ (a)

---

## Part 2 – Counting Models ✏️ *(~8 min)*

Consider a vocabulary with four propositional symbols: $A, B, C, D$.  
There are $2^4 = 16$ possible truth assignments in total.

For each sentence, count how many of the 16 models satisfy it:

**(a)** $(A \land B) \lor (B \land C)$
> 6

**(b)** $A \lor B$
> 12

**(c)** $(A \leftrightarrow B) \leftrightarrow D$
> ~~4~~ 8

---

## Part 3 – Validity and Unsatisfiability ✏️ *(~10 min)*

For each sentence, decide whether it is **valid** (tautology), **unsatisfiable**, or **neither**.  
Briefly justify each answer — a truth table or a short argument is fine.

| | Formula | Valid / Unsat / Neither |
|--|---------|------------------------|
| a | $\text{Smoke} \to \text{Smoke}$ | Valid |
| b | $(\text{Smoke} \to \text{Fire}) \to (\lnot\text{Smoke} \to \lnot\text{Fire})$ | Neither |
| c | $\text{Smoke} \lor \text{Fire} \lor \lnot\text{Fire}$ | Valid |
| d | $((\text{Smoke} \land \text{Heat}) \to \text{Fire}) \leftrightarrow ((\text{Smoke} \to \text{Fire}) \lor (\text{Heat} \to \text{Fire}))$ | Valid |
| e | $(\text{Smoke} \to \text{Fire}) \to ((\text{Smoke} \land \text{Heat}) \to \text{Fire})$ | Valid |
| f | $(\text{Fire} \to \text{Smoke}) \land \text{Fire} \land \lnot\text{Smoke}$ | Unsat |

**(a)**
> $\text{Smoke} \to \text{Smoke} \equiv \neg\text{Smoke} \lor \text{Smoke}$

**(b)**
| Smoke | Fire | $(\text{Smoke} \to \text{Fire})$ | $(\lnot\text{Smoke} \to \lnot\text{Fire})$ | $(\text{Smoke} \to \text{Fire}) \to (\lnot\text{Smoke} \to \lnot\text{Fire})$ |
|-------|------|----------------------------------|--------------------------------------------|-------------------------------------------------------------------------------|
|   F   |   F  |                T                 |                      T                     |                                       T                                       |
|   F   |   T  |                T                 |                      F                     |                                       F                                       |
|   T   |   F  |                F                 |                      T                     |                                       T                                       |
|   T   |   T  |                T                 |                      T                     |                                       T                                       |

**(c)**
> $\text{Fire} \lor \lnot\text{Fire} \vDash \text{Smoke} \lor \text{Fire} \lor \lnot\text{Fire}$

**(d)**
> $(\text{Smoke} \to \text{Fire}) \lor (\text{Heat} \to \text{Fire})$ <br>
> $\equiv (\neg\text{Smoke} \lor \text{Fire}) \lor (\neg\text{Heat} \lor \text{Fire})$ <br>
> $\equiv \neg\text{Smoke} \lor \neg\text{Heat} \lor \text{Fire}$ <br>
> $\equiv \neg(\text{Smoke} \land \text{Heat}) \lor \text{Fire}$ <br>
> $\equiv (\text{Smoke} \land \text{Heat}) \to \text{Fire}$

**(e)**
> $(\text{Smoke} \land \text{Heat}) \to \text{Fire}) \equiv (\text{Smoke} \to \text{Fire}) \lor (\text{Heat} \to \text{Fire})$ und $\text{Smoke} \to \text{Fire} \vDash (\text{Smoke} \to \text{Fire}) \lor (\text{Heat} \to \text{Fire})$

**(f)**
> Fire needs to be True and Smoke False, but then $\text{Fire} \to \text{Smoke}$ implies Smoke is True. Contradiction. 
---

## Part 4 – Normal Forms ✏️ *(~10 min)*

**4.1** Convert the following expressions into **Conjunctive Normal Form (CNF)**:

**(i)** $\lnot(s \to \lnot p) \land (p \to \lnot r)$

**(ii)** $p \leftrightarrow (\lnot q \lor (q \to \lnot p))$

**(iii)** $\lnot(p \to (\lnot q \lor (r \leftrightarrow \lnot p)))$

**4.2** Convert the following expression into **Disjunctive Normal Form (DNF)**:

$(s \to \lnot(\lnot r \to q)) \to p$

---

## Part 5 – Python: Truth Tables 🐍 *(~10 min)*

Open `logic_exercises.ipynb` and go to **Exercise 5**.

You are given a helper that evaluates a formula for one assignment. Your tasks:

**5.1** Complete `truth_table(variables, formula_fn)` to print all rows.

**5.2** Use it to verify your answers from Part 1.2 (the tautology) and Part 3 (validity table).

**5.3** Use it to **count** the number of satisfying models for the formulas in Part 2.

---

## Part 6 – Python: Resolution 🐍 *(~8 min)*

In **Exercise 6** of the notebook you will implement a simple resolution checker.

**6.1** A clause is a set of literals like `{'P', '¬Q', 'R'}`. Complete `resolve(c1, c2)` which returns the resolvent of two clauses (or `None` if they cannot be resolved).

**6.2** Complete `pl_resolution(kb_clauses, goal_clause)` which tries to derive a contradiction from the KB + negated goal.

**6.3** Use it to verify the unicorn problem from the worksheet:
- If the unicorn is mystical → immortal; if not mystical → mortal mammal
- Immortal or mammal → has horn; has horn → magical

Show that **the unicorn is magical**.

---

## Part 7 – First-Order Logic: Formula Matching ✏️ *(~5 min)*

Match each FOL formula to its correct English sentence. Write the letter next to the number.

| # | Formula | Answer |
|---|---------|--------|
| 1 | $\exists x.\ (\text{big}(x) \land \text{cat}(x))$ | |
| 2 | $\exists x.\ (\text{big}(x) \to \text{cat}(x))$ | |
| 3 | $\exists x.\ (\text{big}(x) \lor \text{cat}(x))$ | |
| 4 | $\forall x.\ (\text{big}(x) \land \text{cat}(x))$ | |
| 5 | $\forall x.\ (\text{big}(x) \to \text{cat}(x))$ | |
| 6 | $\forall x.\ (\text{big}(x) \lor \text{cat}(x))$ | |
| 7 | $\forall x.\ (\text{big}(x) \lor \lnot\text{cat}(x))$ | |

**(A7)** All cats are big. **(B2)** There exists a small thing or a cat. **(C5)** All big things are cats.
**(D4)** All things are big cats. **(E)** All cats are small. **(F1)** There exists a big cat.
**(G6)** All small things are cats. **(H3)** There exists a big thing or a cat.

---

## Part 8 – FOL Translation Critique ✏️ *(~5 min)*

For each sentence, decide whether the FOL formula is a **correct** translation. If not, describe the mistake.

**(a)** *"Every apartment in Munich is cheaper than some apartment in Starnberg."*

$$\forall x.\ (\text{App}(x) \land \text{In}(x, \text{Munich}) \to \exists y.\ (\text{App}(y) \land \text{In}(x, \text{Starnberg}) \to \text{Rent}(x) < \text{Rent}(y)))$$
> Wrong. It should be $\text{In}(y, \text{Starnberg})$ instead of $\text{In}(x, \text{Starnberg})$

**(b)** *"There is exactly one apartment in Starnberg with rent below 500€."*

$$\exists x.\ (\text{App}(x) \land \text{In}(x, \text{Starnberg}) \land \forall y.\ (\text{App}(y) \land \text{In}(y, \text{Starnberg}) \land \text{Rent}(y) < 500 \to x = y))$$
> Correct.

**(c)** *"If some apartment is more expensive than any apartment in Munich, it must be in Starnberg."*

$$\forall x.\ (\text{App}(x) \land \forall y.\ (\text{App}(y) \land \text{In}(y, \text{Munich}) \land \text{Rent}(x) > \text{Rent}(y)) \to \text{In}(x, \text{Starnberg}))$$
> ~~Correct.~~ Wrong

---

*Good luck! 🎓*
