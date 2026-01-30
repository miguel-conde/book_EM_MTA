---
name: book-intake
description: "Professional book intake process for technical editors. Establishes global context, target audience, technical scope, and chapter coherence before editorial work begins. Use when starting technical editing projects or need to understand book structure."
---

# Book Intake Workflow

## Stage 0: Pre-Editorial Assessment

Complete this checklist before any chapter editing:

```
Book Intake Progress:
- [ ] Step 0: Create backup of original files
- [ ] Step 1: Complete book-intake.md (global context)
- [ ] Step 2: Build canonical toc.md (chapter structure)
- [ ] Step 3: Map chapter roles (chapter-map.md)
- [ ] Step 4: Establish glossary.md (terminology)
- [ ] Step 5: Validate intake completeness
```

**Step 0: Backup Original Files**

Create comprehensive backup before any editorial work:
- Copy all `.qmd` files to `_originals/` directory with timestamp
- Document current git state (if using version control)
- Verify backup integrity and accessibility

**Step 1: Global Context Assessment**

Complete [book-intake.md](book-intake.md) with:
- Target audience and technical level
- Book objectives and scope boundaries
- Editorial tone and positioning
- Content preservation constraints

**Step 2: Canonical Structure**

Build [toc.md](toc.md) showing:
- Complete table of contents
- Part/chapter organization
- Editorial scope notes

**Step 3: Chapter Role Mapping**

Create [chapter-map.md](chapter-map.md) defining:
- Purpose and scope for each chapter
- Concepts introduced vs assumed
- Technical depth level
- Editorial boundaries (what NOT to do)

**Step 4: Terminology Foundation**

Establish [glossary.md](glossary.md) with:
- Canonical terms and definitions
- Language specifications
- Synonym avoidance rules

**Step 5: Validation**

Ensure intake completeness:
- All files contain project-specific content (no placeholders)
- Chapter progression is logical and coherent
- Technical level is consistent across chapters
- Terminology is standardized

## Quality Standards

### Complete Intake Requirements
- All four intake files must be populated with actual project content
- No template placeholders (e.g., `<TITLE>`, `<Chapter N>`) should remain
- Chapter map must cover every chapter in the TOC
- Glossary must include all key technical terms

### Intake Validation
Before proceeding to editorial work:
1. Review intake files for consistency
2. Verify chapter scope alignment with book objectives
3. Check terminology usage across all intake documents
4. Confirm editorial constraints are clearly specified

## Operational Workflow

### How to Use Intake Artifacts (Critical)

Copilot does not automatically read folders or maintain session memory. The intake artifacts must be **explicitly loaded as context** for each editing session.

**Recommended Mode A: Explicit Context Loading**

```
Per-Session Workflow:
- [ ] Step 1: Load global context into Copilot Chat
- [ ] Step 2: Activate technical-editor agent
- [ ] Step 3: Select and edit target chapter
- [ ] Step 4: Repeat for additional chapters (context persists)
```

**Step 1: Context Loading Command**

At the start of each editing session, use this prompt:

```
Use the following documents as binding editorial context for this session:
- book-intake.md: [paste content]
- toc.md: [paste content] 
- chapter-map.md: [paste relevant chapter section]
- glossary.md: [paste content]

All edits must be consistent with these documents.
```

**Step 2: Agent Activation**

Select the `@technical-editor` agent to apply professional editorial principles.

**Step 3: Chapter Editing**

Open target chapter file, select content, and request editorial improvements. The agent now has:
- Global book context
- Chapter role and scope boundaries
- Terminology standards
- Technical level expectations

**Alternative Mode B: Context-Light Editing**

For quick edits or very independent chapters:
- Use technical-editor agent without loading full context
- Accept potential inconsistencies
- Only recommended for small books or isolated chapters

### Context Consumption Patterns

Each intake artifact serves specific editorial functions:

**book-intake.md → Tone & Standards**
- Sets target audience and technical level
- Defines editorial constraints (content fidelity, language preservation)
- Establishes professional positioning

**toc.md → Conceptual Progression** 
- Prevents premature introduction of concepts
- Maintains appropriate depth progression
- Ensures chapter coherence within book structure

**chapter-map.md → Scope Control**
- Defines what each chapter can/cannot do
- Prevents redundancy and concept repetition
- Guides content organization decisions

**glossary.md → Terminology Consistency**
- Standardizes technical vocabulary
- Eliminates synonym inconsistencies
- Maintains field convention alignment