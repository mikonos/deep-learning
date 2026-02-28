---
name: deep-learning
description: All-in-One Deep Reading tool for Zettelkasten. Designed for deeply digesting books, long-form articles, research reports, and academic papers. Use when a user wants to deeply digest a book/long article/report/paper and build a knowledge network, producing structure notes and atomic notes. Blends Mortimer Adler (structure), Feynman (clarity), Luhmann (network), Pragmatist (actionability), and Critics (debate). Enforces High-Fidelity case preservation and Actionable tool extraction. Keywords: deep reading, structure note, deep learning, Zettelkasten.
---

# Deep Reading

> **Core Philosophy**: Not just understanding the world (Understand), but changing it (Act).
> **Scope**: Book, Long-form Article, Research Report, Academic Paper.

## The Council (Expert Personas)

1.  **Mortimer Adler** (The Architect): Responsible for structure — extracting core propositions and logic trees.
2.  **The Pragmatist** (The Engineer): Responsible for actionability — extracting executable SOPs, templates, and checklists.
3.  **Richard Feynman** (The Teacher): Responsible for clarity — ensuring concepts are demystified and explained in plain language.
4.  **Niklas Luhmann** (The Librarian): Responsible for connectivity — ensuring knowledge is networked and grows organically.
5.  **The Critics** (The Stress Testers): Musk, Socrates, Munger — responsible for stress-testing and debate.

---

## The Iron Rules

1.  **Always Deep**: Regardless of input length, always process at the highest level (structure + tools + debate).
2.  **Case Fidelity**:
    *   **Source text available**: No paraphrasing allowed; atomic notes involving cases or studies must preserve **specific numbers, authors/institutions, timelines, and direct quotes** (page numbers recommended).
    *   **No source text, only summaries or memory**: Mark the note with `Source: book/summary, not verified against original text`; preserve identifiable proper nouns and conclusions; **fabricating details is prohibited**; Feynman review marks "Case Fidelity: Partial (no source text)".
3.  **No Vague Verbs**: Verbs like "optimize," "strengthen," "appropriately" are banned. Every action must be converted into a **specific action** or **quantifiable metric**.
4.  **Metadata Mandatory**: All notes must include YAML Frontmatter (type, tags, links). **No exceptions**.

---

## Storage Rules

1.  **Default Location**: `Daily/YYYY/MM/DD` (or your vault's daily folder, e.g. `05_每日记录/YYYY/MM/DD`)
    *   Get the current date (YYYY, MM, DD); create the date folder if it doesn't exist; create a task folder for this session.
    *   **Task folder naming**: Default to `[Title]_structure_note.md`.
    *   **Structure note naming**: Default to `YYYYMMDD_00_[Title]_structure_note.md`.

2.  **Structure note onboarding** (choose one, see Phase 6):
    *   **Option A**: If the target index has an `## Inbox` section, append this book's entry under Inbox (e.g. `- [[This Structure Note]] — Book Title, YYYYMMDD`).
    *   **Option B**: If the target index has no Inbox, create a new Inbox section.

3.  **Index note onboarding** (see Phase 2.5): Mount the new index note to an existing index, and move it to your index directory (e.g. `Index/` or `03_索引/`); see Phase 2.5 for Inbox/entry format.

---

## The Workflow

**Execution order**: Phase 0 → 1 → 2 → 2.5 → 3 → 4 → 5 → 6 → **6.5 (Workflow Audit, mandatory)**. No skipping; Phase 2.5 must execute immediately after Phase 2; Phase 6.5 must execute immediately after Phase 6.

### Phase 0: Pre-game Plan

Produce an execution plan before starting Phase 1; save as `YYYYMMDD_01_[BookTitle]_execution_plan.md` (same directory as the structure note), and link this file under the Preparation section of task.md.

Must include:
1.  **TODO List** (≥6 items): e.g. full-book argument skeleton, key concepts, argument chains, framework extraction, method extraction, case verification, critical review, network linking.
2.  **Context**: Reading intent (What problem am I trying to solve?).

### Phase 1: Overview & Structure
**Agent**: Mortimer Adler

1.  **Task**: Create the structure note; output must conform to `templates/structure_note_template.md`, including core propositions and supporting logic chains.
2.  **Note**: Invoke `structure-note` skill if available.

### Phase 2: Index Design
**Agent**: Niklas Luhmann
> "Don't ask what category it belongs to — ask who it talks to."

1.  **Task**: Create the index note for this book; output must conform to `templates/index_note_template.md`, including keywords and multiple entry points.
2.  **Note**: Invoke `index-note` skill if available.

### Phase 2.5: Index Note Onboarding
**Agent**: Niklas Luhmann

Execute immediately after index note creation; ensure the new index is accepted into the knowledge network and physically filed.

1.  **Mount to existing index**: In your index directory (e.g. `Index/`), select one or more existing indexes related to this book's topic, and add an entry pointing to this new index note (e.g. under `## Inbox` append `- [[This Index Note]] — Book Title/Topic, YYYYMMDD`, or add to the index's "Theme Structure / Sub-index" section). Ensure bidirectional linking: the new index note's footer should also link back to the parent index.
2.  **Move to index directory**: Move the index note file from the current task directory (e.g. `Daily/...`) to the appropriate location in your index directory:
    *   Use `file-organize` skill if available: determine whether it goes at root level (alongside existing hubs) or in a topic subfolder.
    *   After moving, `[[This Index Note]]` links in the parent index remain valid (filename-only, path-independent).
3.  **(Multi-index mount check deferred to Phase 6)**: Whether notes mentioned in this index should also be mounted to other indexes — check and add entries in Phase 6.

### Phase 3: Recursive Growth
**Agent**: Luhmann & Feynman
> Core innovation: **Create while discovering** (Luhmann Scan).

**Process**:
1.  **Round 1 (Skeleton)**: Starting from the structure note, create all explicitly linked **Atomic Notes (Concepts)**.
2.  **Luhmann Scan (mandatory for every note)**: See `references/luhmann_scan.md`. Three checks — prerequisites, potential connections, **methodology discovery** (if a concept includes an executable "how" → log in task.md, create a detailed Method Note in Phase 4). Record format in task.md: `Prerequisites → Round 2: [[A]]. Connections → Round 3: [[B]]. Methods → [[MethodName]] (Phase 4).`
3.  **Round 2 (Flesh)**: Create the newly discovered notes, continue Luhmann Scan.
4.  **Round 3+ (Edges)**: Until complete or out of scope.

**Atomic Note Specification**:
*   **Template**: `templates/atomic_note_template.md`
*   **Focus**: Definition, Mechanism, Context.
*   **Acceptance**: Feynman Test (a layperson can understand it).

### Phase 4: Methodology Consolidation
**Agent**: The Pragmatist

Turn methods discovered in Phase 3 into Method Notes.

**Method Note Specification** (*high priority*):
1.  **Template**: `templates/method_note_template.md`
2.  **Focus**: Executable Steps (SOP), Templates, Checklists.
3.  **Constraints**:
    *   **No Vague Verbs**: Every step must be concrete.
    *   **Mechanism & Leverage**: Why does it work?
    *   **MVE**: Minimum Viable Experiment as the next step.
4.  **Practitioner-grade requirements ("Operations Manual" not "Academic Exchange")**:
    *   **Steps in tables**: If a method has multiple steps, each step uses a `| Step | What | How | Why |` table clearly separating action items, specific operations, and purpose/mechanism; pure paragraph descriptions of steps are prohibited.
    *   **Inline troubleshooting**: Embed "Common Issue → Immediate Fix" after each step, rather than collecting all pitfalls at the end; the final Pitfalls section serves as a global anti-pattern summary.
    *   **Self-assessment checklist**: Beyond the output acceptance checklist (did the result meet the bar?), add a "Did I execute correctly?" self-check on execution behavior (e.g. process quality, judgment quality, collaboration quality — adjust dimensions by domain).
    *   **Pre-flight section**: Beyond prerequisites, include an independent "Pre-flight Checklist" — things to confirm before starting (environment, materials, mindset, etc.).

### Phase 5: Final Review
**Agent**: Richard Feynman

Review the entire knowledge network through the Feynman lens:
1.  **De-jargon check**: Have all technical terms been "translated" into everyday language?
2.  **Metaphor check**: Do complex concepts have appropriate metaphors?
3.  **Logic check**: Are there any breaks in the argument chain?
4.  **Topology check**: Are there any "surprise" connections?

### Phase 6: Network Review
**Agent**: Niklas Luhmann

1.  **Link check**: Confirm every note (excluding parent-child structure notes) has at least 2 bidirectional links.
2.  **Onboarding**: Complete index onboarding in relevant indexes under your index directory — create `## Inbox` if none exists; file structure notes and atomic notes under appropriate keyword/topic indexes. Invoke `index-note` mode 3 (content onboarding) if available for single or batch onboarding.
3.  **Multi-index mount check**: For every note mentioned in the index (those linked in the keyword section and theme structure section), evaluate whether it should also be mounted to **other** indexes (different lookup intents); if a note is a quality entry point for another topic, add an entry in the corresponding index to enable multi-path discoverability. Output a brief list: `[[NoteA]] → already in Index_X; recommend adding to Index_Y (reason)`.

### Phase 6.5: Workflow Audit (Mandatory)

**Must execute after Phase 6 is complete**. Invoke the **workflow-audit** skill to perform a Deming + Gawande-perspective execution completeness check and systematic closure:

1. **Audit target**: This skill (deep-learning); **artifacts**: all task directory outputs (execution plan, structure note, index, atomic notes, task.md, etc.).
2. **Output**: Save an audit report (`YYYYMMDD_[TaskName]_workflow_audit_report.md`), including item-by-item checklist, system closure, DoD sign-off, multi-index mount list; any item marked ❌ **must be remediated** until all DoD items pass.
3. **workflow-audit main file**: `.cursor/skills/workflow-audit/SKILL.md`; report template: `workflow-audit/references/audit_report_template.md`.

> Cannot be skipped. The workflow is considered incomplete until the audit passes and all gaps are remediated.

---

## Task Tracking

Maintain progress in `task.md`:

```markdown
# Preparation
- [ ] Pre-game Plan Created (≥6 TODOs + Context; in-conversation block or saved file)

# Structure & Index
- [ ] Structure Note Created (Adler)
- [ ] Index Note Created (Luhmann)
- [ ] Index Note Onboarding (Phase 2.5): Mounted to existing index + moved to Index directory

# Extraction Loop (Phase 3)
- [ ] [[NoteA (Concept)]] + Luhmann Scan
- [ ] [[NoteB (Concept)]] + Luhmann Scan

# Methodology (Phase 4)
- [ ] [[ToolA (Method)]] (SOP/Checklist/MVE)

# Review (Phase 5 & 6)
- [ ] Feynman Check (De-jargon check)
- [ ] Network Check (2+ links per note; index onboarding: Inbox or keyword entry; multi-index mount check)

# Workflow Audit (Phase 6.5, mandatory)
- [ ] Invoke **workflow-audit** for execution completeness check (Deming + Gawande perspective), produce audit report, remediate any ❌ items until all DoD items pass
```

---

## Definition of Done

- [ ] **Phase 0**: Execution plan produced (≥6 TODOs + Context).
- [ ] **Overview**: 5 questions answered clearly; Feynman test passed.
- [ ] **Fidelity**: With source text — cases include numbers/proper nouns/direct quotes; without source text — source limitations marked, no fabricated details.
- [ ] **Actionability**: Method Notes contain vague-verb-free steps + reusable templates + practitioner-grade checks (steps with action tables, inline troubleshooting per step, self-assessment checklist, pre-flight checklist).
- [ ] **Network**: All notes bidirectionally reachable (≥2 links); onboarded to relevant indexes (Inbox or keyword entry); this index mounted to existing indexes and filed in index directory; multi-index mount check completed.
- [ ] **Insight**: New connections or unexpected discoveries produced.
- [ ] **Workflow Audit**: Phase 6.5 executed; workflow-audit report produced; all ❌ items remediated; DoD fully passed.
