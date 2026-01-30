---
description: "Creates and manages backups of original book files for safe editorial work. Use before starting any editing project or when you need to restore original content."
---

# Book Backup & Restore

## Important: Template vs Working Files

**Templates** (`.github/skills/book-intake/templates/`): Master templates, never edit directly
**Working copies**: Copied to project root for customization

This backup system protects both your working files AND preserves template integrity.

## Create Initial Backup

Before any editorial work begins, create a complete backup:

### Automatic Backup (Recommended)

```bash
# Create backup directory with timestamp
BACKUP_DIR="_originals/$(date +%Y%m%d_%H%M%S)"
mkdir -p "$BACKUP_DIR"

# Copy all content files
cp *.qmd "$BACKUP_DIR/"
cp *.md "$BACKUP_DIR/" 2>/dev/null || true
cp *.yml "$BACKUP_DIR/" 2>/dev/null || true
cp *.yaml "$BACKUP_DIR/" 2>/dev/null || true

# Create backup manifest
echo "# Backup created: $(date)" > "$BACKUP_DIR/BACKUP_MANIFEST.md"
echo "## Files backed up:" >> "$BACKUP_DIR/BACKUP_MANIFEST.md"
ls -la "$BACKUP_DIR" >> "$BACKUP_DIR/BACKUP_MANIFEST.md"

# Git state (if using version control)
if [ -d .git ]; then
    echo "## Git state:" >> "$BACKUP_DIR/BACKUP_MANIFEST.md"
    git rev-parse HEAD >> "$BACKUP_DIR/BACKUP_MANIFEST.md"
    git status --porcelain >> "$BACKUP_DIR/BACKUP_MANIFEST.md"
fi

echo "✅ Backup created in: $BACKUP_DIR"
```

### Manual Backup

If you prefer manual control:

1. **Create backup directory**: `_originals/YYYYMMDD_project_start/`
2. **Copy all source files**: 
   - All `.qmd` chapter files
   - Configuration files (`_quarto.yml`, etc.)
   - Any supporting `.md` files
3. **Document the state**: Create `BACKUP_MANIFEST.md` with file list and timestamp

## Restore from Backup

### Full Restore

To completely revert to original state:

```bash
# List available backups
ls -la _originals/

# Choose backup directory (replace with actual timestamp)
BACKUP_DIR="_originals/20260130_143000"

# Restore all files (CAUTION: overwrites current files)
cp "$BACKUP_DIR"/*.qmd ./
cp "$BACKUP_DIR"/*.yml ./ 2>/dev/null || true
cp "$BACKUP_DIR"/*.yaml ./ 2>/dev/null || true

echo "✅ Files restored from: $BACKUP_DIR"
```

### Selective Restore

To restore only specific files:

```bash
# Restore single chapter
cp "_originals/20260130_143000/03-EM-paso-a-paso.qmd" ./

# Restore multiple chapters  
cp "_originals/20260130_143000"/{01-problema,02-modelo-base}.qmd ./
```

### Compare with Original

To see what has changed:

```bash
# Compare current file with original
diff "03-EM-paso-a-paso.qmd" "_originals/20260130_143000/03-EM-paso-a-paso.qmd"

# Or use git-style diff (if available)
git diff --no-index "_originals/20260130_143000/03-EM-paso-a-paso.qmd" "03-EM-paso-a-paso.qmd"
```

## Backup Management

### Directory Structure

Recommended backup organization:

```
_originals/
├── 20260130_143000_initial/          # Project start backup
│   ├── BACKUP_MANIFEST.md
│   ├── *.qmd
│   └── _quarto.yml
├── 20260205_120000_before_edit/      # Before major editing
│   ├── BACKUP_MANIFEST.md
│   └── *.qmd
└── 20260210_160000_checkpoint/       # Editorial checkpoint
    ├── BACKUP_MANIFEST.md
    └── *.qmd
```

### Backup Best Practices

1. **Initial backup**: Before any AI-assisted editing begins
2. **Checkpoint backups**: Before major editorial sessions
3. **Feature backups**: Before experimenting with new approaches
4. **Version documentation**: Always include manifest with timestamp and context

### Integration with Git

If using Git version control:

```bash
# Stage original state
git add .
git commit -m "Original content before AI editorial work"

# Create tag for easy reference
git tag v0.0-original

# For restore, simply:
git checkout v0.0-original -- *.qmd
```

## Workflow Integration

### With Book Intake Process

```
Editorial Workflow:
1. [ ] Create initial backup (this prompt)
2. [ ] Complete book intake (book-intake skill)
3. [ ] Load editorial context (/load-context prompt)
4. [ ] Edit chapters (technical-editor agent)
5. [ ] Create checkpoint backup (this prompt)
```

### With Technical Editor

Before major editorial sessions:
1. Create checkpoint backup with descriptive name
2. Document what editing phase you're starting
3. Proceed with confidence knowing you can revert

### Emergency Recovery

If editing goes wrong:
1. Stop editing immediately
2. Use "Compare with Original" to assess changes
3. Restore from most recent good backup
4. Review what went wrong before resuming

## Quality Assurance

### Backup Verification

Always verify your backups:

```bash
# Check file integrity
diff -q *.qmd _originals/latest/*.qmd

# Verify file count matches
echo "Original files: $(ls *.qmd | wc -l)"
echo "Backup files: $(ls _originals/latest/*.qmd | wc -l)"
```

### Recovery Testing

Periodically test your restore process:
1. Create test backup
2. Make small change to one file  
3. Practice restore procedure
4. Verify successful recovery