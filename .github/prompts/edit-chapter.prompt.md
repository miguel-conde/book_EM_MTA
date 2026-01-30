---
agent: technical-editor
description: "Edit a single chapter with professional technical editing standards, optionally loading book context for consistency."
---

# Edit Single Chapter

Edit the provided chapter content using professional technical editing standards. This prompt provides a streamlined workflow for focused chapter editing.

## Workflow Options

Choose your editing approach based on available context:

### Option A: Context-Aware Editing (Recommended)
If you have book intake files (book-intake.md, toc.md, chapter-map.md, glossary.md) available:

1. **Load Context First**: Run `/load-context` to establish global editorial context
2. **Then Edit**: Provide the chapter content for editing with full book awareness

### Option B: Standalone Editing
For isolated chapter editing without broader book context:

1. **Direct Edit**: Provide chapter content and any specific requirements
2. **Manual Context**: Include any relevant terminology, audience, or consistency requirements in your request

## Chapter Content Input

Provide the chapter content in one of these ways:
- **Attached file**: Attach the .qmd/.md chapter file 
- **Selected text**: Select chapter content and reference with `${selection}`
- **File reference**: Reference specific file with `${file}`
- **Paste content**: Include chapter text directly in your message

## Editing Instructions

Transform the chapter content to meet professional publishing standards:

### Content Preservation
- Maintain all technical accuracy and mathematical formulations
- Preserve existing language exactly
- Keep all code examples, diagrams, and cross-references intact
- Retain educational value and conceptual progression

### Style Transformation  
- Convert from informal/conversational to professional technical prose
- Remove chat artifacts, emojis, and conversational transitions
- Improve paragraph structure and logical flow
- Enhance clarity while maintaining technical depth
- Transform content into polished, publication-ready narrative prose
- Use active voice and varied sentence structure for engaging technical writing

### Visual Emphasis and Structure
- Apply **bold formatting** for key technical terms, critical concepts, and important results
- Use *italic formatting* for mathematical variables, conceptual distinctions, and emphasis
- Format `code elements` appropriately for technical identifiers and functions
- Assess chapter structure and add introduction/summary sections if genuinely missing and needed
- Ensure smooth transitions between major sections for coherent narrative flow

### Consistency Requirements
- Apply consistent terminology (use loaded glossary if available)
- Maintain appropriate technical level for target audience
- Ensure smooth conceptual progression within chapter scope
- Follow established mathematical notation standards

## Output Expectations

Return the fully edited chapter that:
- Reads as professional technical documentation with polished prose composition
- Maintains full technical accuracy and preserves all existing content
- Flows logically within its scope with enhanced narrative structure
- Uses appropriate visual emphasis (bold/italics) for key concepts and technical terms
- Includes introduction/summary sections only if structurally missing and needed
- Is ready for publication without further content changes
- Preserves all Quarto/Markdown formatting and syntax

## Usage Examples

**With Context Loading:**
```
/load-context
[After context loads]
/edit-chapter #file:chapter-3.qmd
```

**Standalone Editing:**
```
/edit-chapter #file:chapter-5.qmd

Focus on improving clarity for data science practitioners. 
Ensure mathematical notation follows standard conventions.
```

**Selected Content:**
```
/edit-chapter 

Edit this selected chapter section: ${selection}
Target audience: technical practitioners with basic statistics background
```

## Quality Assurance

The edited content will be checked for:
- Professional tone and polished prose composition
- Technical accuracy preservation and content integrity
- Consistent formatting and structure with appropriate visual emphasis
- Proper use of bold/italics for key concepts and technical elements
- Appropriate audience level and pedagogical flow
- Smooth transitions and logical narrative progression
- Complete chapter structure (introduction/summary if needed)
- Publication readiness