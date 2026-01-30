---
description: Fix ill-formed LaTeX math equations in Quarto .qmd files using systematic patterns
agent: agent
---

Fix all ill-formed LaTeX math equations in the specified .qmd file(s). If no files are specified, politely ask which files need fixing.

## Common LaTeX Issues to Fix

**Escaped Characters:**
- `\\lambda`, `\\beta`, `\\sum` → `\lambda`, `\beta`, `\sum`
- `\_`, `\^` → `_`, `^` (within math contexts)
- `\{`, `\}` → `{`, `}`

**Malformed Display Math:**
- `\[\ ... \]` (with stray backslashes) → `$$ ... $$`
- `\[ ... \\` (incomplete blocks) → `$$ ... $$`

**Pseudo-Math in Parentheses:**
- `(X_h)`, `(\beta^*)`, `(z_{h,b})` → `$X_h$`, `$\beta^*$`, `$z_{h,b}$`

**Corrupted Commands:**
- `\mathbb{E}\[` → `\mathbb{E}[`
- `\mathcal{H}*b`, `\mathcal{H}\_b` → `\mathcal{H}_b`
- `z*{h,b}`, `z\^\*\_{h,b}` → `z_{h,b}`
- Tab-corrupted commands like `	ext{con}` → `\text{con}`
- Missing backslashes: `ilde`, `ext{`, `um_` → `\tilde`, `\text{`, `\sum_`

**Quarto-Specific:**
- Use `$$...$$` for display math (not `\[...\]`)
- Use `$...$` for inline math
- Use `\operatorname{}` for function names like Poisson, Gamma
- Ensure proper spacing around math blocks

## Systematic Approach

1. **Scan first** with grep/search for common patterns: `\\\[`, `\\\]`, `\\_`, `\\\^`, `z\*\{`, `mathcal\{H\}\*`
2. **Read sections** containing math to understand context
3. **Apply fixes** using precise string replacement
4. **Verify** no broken patterns remain

## Quality Standards

- Math must render cleanly in Quarto
- Preserve mathematical meaning exactly
- Use consistent notation throughout
- Follow LaTeX best practices
- Test complex expressions for proper grouping