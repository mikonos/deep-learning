# Luhmann Scan Workflow

> This is the skill's core innovation: **create while discovering**.

---

## What Is a Luhmann Scan?

A standardized set of questions executed after creating each atomic note:

### Question 1: Prerequisites
> "To fully understand this card, what other notes are needed?"

**Think about**:
- What undefined terms does this card reference?
- What more fundamental concepts does this card's argument rest on?
- If a reader hasn't read X, can they understand this card?

### Question 2: Potential Connections
> "What related concepts does this card imply?"

**Think about**:
- Does this concept have counterparts in other domains?
- Are there "opposites" or "alternatives"?
- What are the application scenarios for this concept?

### Question 3: Methodology Discovery
> "When this concept (what) is discussed, does the source also describe an executable methodology (how)?"

**Think about**:
- Does the book provide steps, checklists, templates, or exercises?
- If yes, create a Method Note immediately.

---

## Handling Scan Results

Discovered potential notes are classified by **round**:

| Round | Definition | Source |
|-------|-----------|--------|
| **Round 1** | Explicit links | Directly mentioned in the structure note / index note |
| **Round 2** | Implicit dependencies | Discovered during the Round 1 Luhmann Scan |
| **Round 3** | Peripheral expansion | Discovered during the Round 2 Luhmann Scan |

---

## Example

### Input Note: [[Hedonic Treadmill]]
After creating this note, run the Scan:

**Question 1: Prerequisites**
- To understand the "hedonic treadmill," you need to know what **dopamine** is → [[Dopamine Prediction Error]]
- This effect is an evolutionary product → [[Natural Selection's Illusion Mechanisms]] (already in Round 1)

**Question 2: Potential Connections**
- Is this the same thing as "hedonic adaptation" in economics? → [[Hedonic Adaptation]]
- Are there ways to break the treadmill? → [[Dopamine Fasting]]
- How does Buddhism view this? → [[Craving (Taṇhā)]]

**Question 3: Methodology Discovery**
- If the book provides specific exercises for "breaking the hedonic treadmill" (e.g. dopamine fasting steps) → [[Dopamine_Fasting_SOP]] (create in Phase 4); in this example, none found.

**Scan Results**:
- Round 2: [[Dopamine Prediction Error]]
- Round 3: [[Hedonic Adaptation]], [[Dopamine Fasting]], [[Craving (Taṇhā)]]
- Methods: None (if found, write `[[MethodName]] (Phase 4)`)

---

## Recording in task.md

One-line Scan summary per card, format:

```markdown
- [x] **[[Hedonic Treadmill]]** (Mechanism)
    - *Luhmann Scan*: Prerequisites → Round 2: [[Dopamine Prediction Error]]. Connections → Round 3: [[Hedonic Adaptation]], [[Dopamine Fasting]], [[Craving (Taṇhā)]]. Methods → (none; if found, write [[MethodName]] Phase 4)
```

---

## When to Stop?

1. **User explicitly stops**
2. **Newly discovered notes are outside the book's scope** (e.g. relating to a completely different discipline)
3. **Diminishing returns**: Round 3+ notes contribute little to understanding this book

> Remember: The goal is to **understand this book**, not to build an encyclopedia.
