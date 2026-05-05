# Worksheet: Knowledge Representation & Ontologies
**Foundations of Artificial Intelligence – SS 2026**
*University of Bremen, Institute for Artificial Intelligence*

---

> **Instructions:** Written tasks (✏️) answer here or in a Markdown cell. Programming tasks (🐍) go in `ontology_exercises.ipynb`. Estimated time: **~45 minutes**.

---

## Part 1 – Conceptual Questions ✏️ *(~10 min)*

**1.1** What are the three components of a Description Logic knowledge base? Briefly describe what each stores.

**1.2** Consider the following facts:

```
Ben is a human.       Sarah is a human.
Ben owns Rex.         Sarah owns Kittypillar.
Rex is a dog.         Kittypillar is a cat.
```

Answer these questions under **both** assumptions and explain the difference:

| Question | Closed-World Assumption | Open-World Assumption |
|----------|------------------------|----------------------|
| Does Ben own a dog? | | |
| Does Ben own a cat? | | |
| Is Rex a cat? | | |

**1.3** What is the difference between an **Ontology** and a **Knowledge Graph**? Use the TBox/ABox terminology in your answer.

**1.4** Match each ALC construct to its meaning:

| Construct | Meaning |
|-----------|---------|
| $\top$ | |
| $\bot$ | |
| $C \sqcap D$ | |
| $C \sqcup D$ | |
| $\exists r.C$ | |
| $\forall r.C$ | |
| $C \sqsubseteq D$ | |

**1.5** Identify whether each of the following belongs to the **TBox**, **ABox**, or **RBox**:

| Statement | T / A / R |
|-----------|-----------|
| `Cat ⊑ Mammal` | |
| `Mother(julia)` | |
| `dreams ⊑ sleeps` | |
| `HappyCatOwner ⊑ ∃owns.Cat` | |
| `ParentOf(julia, max)` | |
| `Dis(sleeps, runs)` | |

---

## Part 2 – Reading DL Axioms ✏️ *(~5 min)*

Translate each DL axiom into plain English:

**(a)** `Lecturer ⊑ ∃teaches.Lecture`

**(b)** `Mother ≡ Female ⊓ Parent`

**(c)** `Male ⊓ Female ⊑ ⊥`

**(d)** `HappyCatOwner ⊑ ∃owns.Cat ⊓ ∀caresFor.Healthy`

**(e)** `owns ⊑ caresFor` *(RBox)*

---

## Part 3 – Writing DL Axioms ✏️ *(~5 min)*

Write DL axioms (TBox / ABox / RBox entries) for the following statements. Use your own concept and role names.

**(a)** Every student is a person.

**(b)** A vegetarian is a person who only eats plant-based food.

**(c)** No person can be both alive and dead at the same time.

**(d)** Every robot has at least one sensor.

**(e)** If a robot perceives something, it is aware of it. *(RBox)*

**(f)** The individual `tiago` is a robot located in the kitchen. *(ABox)*

---

## Part 4 – Design Your Own Ontology 🐍 *(~25 min)*

Open `ontology_exercises.ipynb` and complete **Exercise 4**.

You will build a small **kitchen robot ontology** using Python's `owlready2` library, then run a reasoner to derive new facts automatically.

**4.1** Define the TBox — add the classes and properties provided, then add **two of your own**.

**4.2** Populate the ABox — add the individuals provided, then add **one of your own**.

**4.3** Run the HermiT reasoner and inspect what new facts were inferred.

**4.4 (Bonus):** Introduce an inconsistency (e.g. make an individual both `Alive` and `Dead`) and observe what the reasoner reports.

---

*Good luck! 🎓*
