---
description: "Editorial guidelines for technical book content ensuring clarity, consistency, and professional tone"
applyTo: '**/*.{qmd,md}'
---

# Editorial Instructions — Mandatory and Non-Negotiable

These instructions define the editorial contract.

---

## 0. Global Book Awareness (Precondition)

Before editing any chapter or section:

- Assume knowledge of the full book structure and table of contents.
- Respect:
  - The progression of concepts across chapters
  - The intended level of depth for each chapter
  - Terminology consistency across the book

Edits must not introduce contradictions or redundancy with other chapters.

---

## 1. Language Policy

- Preserve the original language(s) exactly.
- Do NOT translate or normalize language.
- Mixed-language content must remain mixed unless instructed otherwise.

---

## 2. Content Integrity (Absolute)

- Preserve the content **100%**.
- Do NOT:
  - Add ideas or examples
  - Remove explanations
  - Change scope or intent

Allowed:
- Rephrasing for clarity
- Paragraph and section restructuring
- Logical reordering of existing material
- Expansion of compressed explanations using only existing ideas

---

## 3. Tone and Editorial Style

Target style:
- Professional
- Didactic
- Precise
- Calm and authoritative

Reference:
> High-quality online technical books and long-form technical essays.

### Prose-Oriented Composition
Transform all content into polished, publication-ready prose:

- **Conversational to professional**: Convert chat-style, informal explanations into structured technical prose
- **Narrative flow**: Ensure ideas progress logically with smooth transitions between concepts
- **Sentence variety**: Mix sentence lengths and structures for engaging technical writing
- **Active voice preference**: Use active voice where possible for clarity and directness
- **Paragraph coherence**: Each paragraph should focus on a single main idea with supporting details
- **Technical storytelling**: Frame technical concepts within clear explanatory narratives

### Style Transformation Rules:
- Remove emojis and chat artifacts
- Remove conversational tone and rhetorical questions
- Avoid motivational language and informal expressions
- Transform bullet points into flowing prose where appropriate
- Convert fragmented explanations into coherent paragraphs
- Maintain technical precision while improving readability

---

## 4. Structure and Organization

- Enforce consistent heading hierarchy:
  - `#` Chapter
  - `##` Section
  - `###` Subsection
- Headings must be descriptive and technical.
- Restructuring is allowed if it improves clarity and aligns with book-level logic.

### Chapter Structure Assessment
When editing chapters, evaluate and enhance structural completeness:

- **Introduction sections**: Assess if chapter needs clear introduction that:
  - Establishes chapter scope and objectives
  - Connects to previous chapters' concepts
  - Previews key learning outcomes
  - Only add if structurally missing and improves pedagogical flow

- **Summary/conclusion sections**: Evaluate if chapter benefits from:
  - Synthesis of key concepts covered
  - Connection to upcoming chapters
  - Reinforcement of main takeaways
  - Only add if missing and needed for chapter coherence

- **Transitional elements**: Ensure smooth flow between major sections
- **Logical progression**: Verify concepts build appropriately throughout chapter

**Note**: Only add structural sections when genuinely missing and necessary for chapter coherence. Always preserve existing content 100%.

---

## 5. Formatting and Technical Standards

### Mathematical Notation
- Use consistent mathematical notation throughout the book
- Ensure proper LaTeX formatting in technical documents:
  - Display math: `$$...$$` (not `[...]` or `\[...\]`)
  - Inline math: `$...$`
  - Function names: `\operatorname{FunctionName}`
- Maintain consistent symbol definitions across chapters
- Preserve mathematical spacing and alignment

### Code Integration
- Ensure prose explanations align with code implementations
- Maintain consistency between mathematical formulations and computational examples
- Preserve code block formatting and syntax highlighting

### Cross-References and Links
- Preserve all internal references, citations, and cross-links
- Ensure terminology usage is consistent with earlier definitions
- Maintain coherent notation across mathematical derivations

### Quarto/Markdown Compatibility
- Preserve valid Quarto Markdown syntax
- Keep specialized markup (callouts, cross-references, etc.) intact
- Ensure compatibility with target output formats

### Visual Emphasis and Formatting
Apply consistent visual emphasis to enhance readability and comprehension:

- **Bold formatting** (`**text**`) for:
  - Key technical terms on first definition
  - Critical concepts that readers must remember
  - Important algorithmic steps or decision points
  - Essential mathematical results or conclusions

- **Italic formatting** (`*text*`) for:
  - Mathematical variables and parameters in prose
  - Emphasis on conceptual distinctions
  - Foreign terms or domain-specific jargon
  - Subtle but important qualifications or conditions

- **Code formatting** (`` `text` ``) for:
  - Function names, variable names, and code elements in prose
  - File names, command line instructions
  - Specific parameter values and technical identifiers

**Emphasis Guidelines:**
- Use visual aids strategically, not excessively
- Ensure formatting enhances rather than distracts from content
- Maintain consistency in formatting decisions across chapters
- Prioritize technical accuracy over visual appeal

---

## 6. Multi-Audience Considerations

Many technical books serve multiple reader types. When editing:

- **Preserve technical rigor** for expert practitioners
- **Maintain accessibility** for business stakeholders and students  
- **Support progressive learning** from foundational to advanced concepts
- **Balance mathematical precision** with intuitive explanations
- **Respect pedagogical frameworks** (analogies, worked examples, step-by-step derivations)

Adapt explanations to serve all intended audiences without sacrificing accuracy.

---

## 7. Technical Accuracy Requirements

- **Verify consistency** between mathematical notation and computational examples
- **Preserve precise technical distinctions** and definitions
- **Maintain logical progression** of technical concepts
- **Ensure algorithmic descriptions** match implementation details
- **Respect domain-specific conventions** and established terminology

---

## 8. Forbidden Behaviors

You must NOT:
- Ask questions to the reader
- Add summaries unless requested
- Use informal language
- Introduce new content

You are editing a book, not a standalone article.

---

## 9. Domain-Specific Guidance

For specialized technical domains:

- **Consult available skills** in `.github/skills/` directory for domain expertise
- **Check context files** in `.github/context/` for project-specific methodologies
- **Apply field-specific conventions** while maintaining editorial principles
- **Preserve established terminology** and notation standards for the domain

When domain guidance conflicts with general principles, prioritize technical accuracy and reader comprehension.
