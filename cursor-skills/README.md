# Cursor IDE Skills

Skills for **Cursor IDE** (not Claude Code terminal). These use Cursor's skill format with `SKILL.md` files and YAML frontmatter.

## Installation

Copy to your global Cursor skills directory:

```bash
cp -r cursor-skills/* ~/.cursor/skills/
```

Or clone and symlink:

```bash
git clone https://github.com/simeond/claude-code-r-skills.git ~/repos/claude-code-r-skills
ln -s ~/repos/claude-code-r-skills/cursor-skills/referee-report ~/.cursor/skills/referee-report
ln -s ~/repos/claude-code-r-skills/cursor-skills/viva-qa ~/.cursor/skills/viva-qa
```

## Available Skills

### referee-report

Journal-calibrated referee report generator for academic papers. Auto-detects paper type (structural vs reduced-form) and applies appropriate sanity checks.

**Usage:** Ask Cursor to generate a referee report for your paper:
> "Generate a referee report for my paper at `_project/papers/my_paper/` for QJE"

**Features:**
- Supports multiple journals (ECMA, QJE, JPE, RESTUD, RAND, MKTSC, etc.)
- Three modes: `full` (3.5–5.5k words), `quick` (800–1200 words), `re-review`
- Auto-detects structural vs reduced-form methodology
- Outputs timestamped markdown to `assets/referee_report/`

### viva-qa

PhD viva preparation Q&A generator from referee reports. Synthesises concerns across multiple journal calibrations into exam-style questions with strategic answers.

**Usage:** After generating referee reports:
> "Use the viva-qa skill to create viva preparation from my referee reports"

**Features:**
- Extracts recurring concerns across reports
- Generates Big Picture, Methods, Results, and Technical Q&A sections
- Includes Quick-Fire Defence Statements and Key Numbers to Memorise
- Adapts question focus based on paper type (structural vs reduced-form)

## Difference from Claude Code Skills

| Feature | Claude Code (`.claude/`) | Cursor (`~/.cursor/skills/`) |
|---------|--------------------------|------------------------------|
| Location | Project `.claude/skills/` | Global `~/.cursor/skills/` |
| Format | Markdown folders | `SKILL.md` with YAML frontmatter |
| Activation | Pattern matching | Glob patterns, auto-detection |
| IDE | Terminal | Cursor IDE |
