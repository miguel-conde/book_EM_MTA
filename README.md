# Technical Book Editing with AI Agents

A professional framework for editing technical books using VSCode Copilot custom agents, ensuring global coherence, terminology consistency, and publication-ready quality.

## 📖 Overview

This repository contains a complete **agentic framework** for professional technical book editing that treats chapters as parts of a cohesive whole rather than isolated documents. The system combines:

- **Book Intake Process**: Establishes global context before any editing begins
- **Technical Editor Agent**: Professional editing with domain expertise
- **Specialized Skills**: Domain-specific knowledge (EM/MTA methodology)
- **Workflow Integration**: Systematic, repeatable editorial processes

## 🏗️ System Architecture

```
📁 .github/
├── 🤖 agents/
│   └── technical-editor.agent.md      # Main editorial agent
├── 🧠 skills/
│   ├── book-intake/                   # Global context establishment  
│   │   ├── SKILL.md                   # Intake workflow
│   │   └── templates/                 # Master templates (copy to project root)
│   │       ├── book-intake.md         # Book context template
│   │       ├── toc.md                 # Table of contents template
│   │       ├── chapter-map.md         # Chapter roles template
│   │       └── glossary.md            # Terminology template
│   └── em-mta-methodology/            # Domain expertise
│       └── SKILL.md                   # EM/MTA technical knowledge
├── 📝 prompts/
│   ├── backup-restore.prompt.md       # Backup & recovery operations
│   ├── load-context.prompt.md         # Context loading helper
│   └── technical-editing.prompt.md    # Editorial prompts
└── 📋 instructions/
    └── technical-edition.instructions.md  # Global guidelines
```

## 🚀 Quick Start

### Prerequisites

- VSCode with GitHub Copilot extension
- This repository cloned and opened in VSCode
- GitHub Copilot access enabled
- **Important**: Original files backed up (see Step 0 below)

### Step 0: Create Backup (Essential First Step)

Before any editorial work, create a complete backup of original files:

1. **Create backup using our prompt**:
   ```
   /backup-restore
   ```

2. **Run the backup script** or manually copy files to `_originals/` directory

3. **Verify backup integrity** - ensure all .qmd files are safely stored

> **Why this matters**: Professional editors always preserve originals. This enables fearless editing and emergency recovery.

### Step 1: Complete Book Intake (One-time setup)

Before any editorial work, establish the global book context:

1. **Copy intake templates to your project root**:
   ```bash
   # Copy templates from framework to working directory
   cp .github/skills/book-intake/templates/* .
   ```

2. **Activate the book-intake skill** in Copilot Chat:
   ```
   @copilot Use the book-intake skill to set up editorial context
   ```

3. **Complete the copied intake documents** (now in your project root):
   - `book-intake.md`: Target audience, technical level, editorial constraints
   - `toc.md`: Complete table of contents and chapter structure
   - `chapter-map.md`: Purpose and scope for each chapter
   - `glossary.md`: Canonical terminology and definitions

> **Important**: Never edit the template files directly in `.github/skills/book-intake/templates/`. Always work with copies in your project root.

### Step 2: Load Context for Editing Session

For each editing session, load the global context:

1. **Use the context loading prompt**: 
   ```
   /load-context
   ```

2. **Fill in the template** with content from your intake files:
   - Paste `book-intake.md` content
   - Paste `toc.md` content  
   - Paste relevant chapter section from `chapter-map.md`
   - Paste `glossary.md` content

### Step 3: Edit Chapters

With context loaded, edit chapters professionally:

1. **Activate the technical-editor agent**:
   ```
   @technical-editor
   ```

2. **Select chapter content** and request editing:
   ```
   Edit this chapter following the loaded editorial context
   ```

The agent will automatically:
- Apply domain expertise (EM/MTA methodology if relevant)
- Respect chapter scope boundaries
- Maintain terminology consistency
- Preserve content fidelity while improving flow

## 📋 Detailed Workflows

### Book Intake Workflow (Stage 0)

Complete this **once per book project**:

```
Book Intake Checklist:
- [ ] Create backup of all original files (_originals/ directory)
- [ ] Copy intake templates from .github/skills/book-intake/templates/ to project root
- [ ] Define target audience and technical level (book-intake.md)
- [ ] Map complete chapter structure (toc.md)  
- [ ] Specify each chapter's role and boundaries (chapter-map.md)
- [ ] Standardize key terminology (glossary.md)
- [ ] Validate intake completeness
```

**Why this matters**: Prevents chapter inconsistencies, terminology drift, and scope creep that plague AI-assisted writing projects.

### Editorial Session Workflow (Stage 1)

For **each editing session**:

```
Editorial Session Checklist:
- [ ] Verify backup exists and is current
- [ ] Load global context using /load-context prompt
- [ ] Activate @technical-editor agent
- [ ] Analyze chapter against its defined scope
- [ ] Apply domain expertise from skills
- [ ] Execute editorial improvements
- [ ] Validate consistency with intake context
- [ ] Verify content fidelity preservation
- [ ] Create checkpoint backup (optional, for major changes)
```

## 🎯 Key Benefits

### Global Coherence
- **No isolated editing**: Every chapter edited with full book awareness
- **Consistent progression**: Concepts introduced in logical order
- **Terminology alignment**: Standardized technical vocabulary

### Professional Quality
- **Content fidelity**: 100% preservation of original ideas and conclusions
- **Editorial standards**: Publication-ready technical prose
- **Domain expertise**: Specialized knowledge applied automatically

### Systematic Process
- **Repeatable workflow**: Consistent results across editing sessions  
- **Quality validation**: Built-in consistency checks
- **Scalable approach**: Works for books of any size

## 📝 Example Usage Scenarios

### Scenario 1: New Book Project

```bash
# 0. Create initial backup
/backup-restore
# Run the backup script to create _originals/ directory

# 1. Copy intake templates
cp .github/skills/book-intake/templates/* .

# 2. Complete book intake
@copilot Use book-intake skill to establish editorial context

# 3. Fill out all copied intake templates in project root

# 4. Start editing first chapter
/load-context
# (Fill template with intake content)

@technical-editor Edit chapter 1 following the loaded context
```

### Scenario 2: Ongoing Chapter Editing

```bash
# Verify backup exists
ls _originals/

# Load context and edit
/load-context  
# (Use same intake content from previous sessions)

@technical-editor Edit chapter 5, ensuring consistency with previous chapters
```

### Scenario 3: Major Editorial Changes

```bash
# Create checkpoint backup before major changes
/backup-restore
# Choose "Create checkpoint backup"

# Proceed with editing
@technical-editor Restructure chapters 3-5 for better flow
```

### Scenario 4: Recovery from Problems

```bash
# Something went wrong, compare with original
/backup-restore
# Use "Compare with Original" option

# Restore if needed  
/backup-restore
# Choose "Selective Restore" or "Full Restore"
```

## 🔧 Customization

### Adding Domain Skills

To add expertise for other technical domains:

1. **Create new skill directory**: `.github/skills/your-domain/`
2. **Follow the skill template**: Use `em-mta-methodology` as reference
3. **Include usage examples**: Specific input/output patterns
4. **Reference in agent**: Technical editor will automatically apply

### Adapting for Other Book Types

To use this framework for different types of technical books:

1. **Update book-intake templates**: Adjust for your audience/domain
2. **Modify glossary structure**: Include your field's terminology
3. **Customize editorial principles**: Adapt formatting standards
4. **Add domain skills**: Include relevant technical expertise

## ⚡ Advanced Features

### Multi-Language Support
- Preserves original language(s) exactly
- Maintains consistency across multilingual content
- Respects cultural and linguistic conventions

### Mathematical Notation
- Standardizes LaTeX formatting across chapters
- Ensures symbol consistency (e.g., $\omega$ for exposure)
- Validates equation-to-prose alignment

### Code Integration
- Preserves computational examples exactly
- Ensures code-prose consistency
- Maintains functional cross-references

## 🧪 Quality Validation

The framework includes multiple validation layers:

- **Intake validation**: Ensures complete context establishment
- **Scope validation**: Checks chapter boundaries respect
- **Terminology validation**: Verifies glossary compliance
- **Content validation**: Confirms fidelity preservation
- **Consistency validation**: Ensures book-level coherence

## 📚 Best Practices

### For Optimal Results

1. **Always backup first**: Never edit without original files safely stored
2. **Copy templates, don't edit them**: Work with copies in project root, preserve master templates
3. **Complete intake thoroughly**: Don't skip the context establishment
4. **Load context every session**: Copilot doesn't retain memory between sessions
5. **Edit systematically**: Follow the checklist workflows
6. **Validate frequently**: Check consistency across chapters
7. **Update intake iteratively**: Refine context as book evolves
8. **Create checkpoint backups**: Before major editorial changes

### Common Pitfalls to Avoid

- **No backup strategy**: Risk losing original work forever
- **Editing templates directly**: Corrupts master templates for future projects
- **Skipping book intake**: Results in inconsistent chapters
- **Editing without context**: Loses global coherence
- **Incomplete glossaries**: Leads to terminology drift
- **Ignoring scope boundaries**: Creates redundant content
- **No recovery plan**: Panic when things go wrong

## 🤝 Contributing

This framework follows VSCode Copilot best practices and Agent Skills specifications. When contributing:

- Follow the established patterns in existing skills
- Include comprehensive usage examples
- Maintain the checklist workflow approach
- Ensure all content is project-agnostic (specific details go in context files)

## 📄 License

This agentic framework is designed for professional technical book editing. Adapt and extend for your specific editorial needs.

---

**Ready to transform your technical writing process?** Start with the book intake workflow and experience professional-quality AI-assisted editing that treats your book as a coherent whole.