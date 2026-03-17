# dashi-skills Repository Guide

## Repository Information

This is [limerick](https://github.com/limerick)'s personal skills repository for storing and managing Claude Code custom skills.

**Repository Structure:**

```
dashi-skills/
├── AGENTS.md           # This file, instructions for AI assistants
├── README.md           # English documentation
├── README.zh.md        # Chinese documentation
├── skills/             # Skills storage directory
│   ├── skill-name-1/
│   │   ├── SKILL.md
│   │   └── ...
│   └── skill-name-2/
│       ├── SKILL.md
│       └── ...
└── skills-lock.json    # Skills dependency lock file
```

## Notes for Using skill-creator

### 1. Skill Directory Location

**IMPORTANT:** When creating new skills in this repository, skills MUST be placed in:

```bash
/Users/bytedance/project/github/dashi-skills/skills/<skill-name>/
```

**DO NOT** create skills in other locations such as:
- ❌ `~/.claude/skills/`
- ❌ `/tmp/`
- ❌ Repository root directory

### 2. Workspace Directory

Testing and iteration workspace should be created at:

```bash
/Users/bytedance/project/github/dashi-skills/<skill-name>-workspace/
```

This keeps the workspace at the same level as the skill directory for easier management.

### 3. Complete Skill Creation Workflow

When using `/skill-creator` to create a new skill:

1. **Confirm target directories**

   ```bash
   # Skill directory
   SKILL_DIR="/Users/bytedance/project/github/dashi-skills/skills/<skill-name>"

   # Workspace directory
   WORKSPACE_DIR="/Users/bytedance/project/github/dashi-skills/<skill-name>-workspace"
   ```

2. **Create skill structure**

   ```bash
   mkdir -p "$SKILL_DIR"
   # Create SKILL.md and other resources in SKILL_DIR
   ```

3. **Run tests**

   ```bash
   mkdir -p "$WORKSPACE_DIR/iteration-1"
   # Run test cases in workspace
   ```

4. **Package skill**

   ```bash
   python -m scripts.package_skill "$SKILL_DIR"
   # Generates <skill-name>.skill file
   ```

### 4. Skill Naming Conventions

- Use lowercase letters and hyphens: `skill-name`
- Avoid underscores or camelCase
- Prefer the naming pattern `theory-object-action`
- The `object` segment is optional, so `theory-action` is also valid
- Let the `theory` segment express the guiding lens, method, or conceptual framework
- Let the `object` segment name the domain or target when needed
- Let the `action` segment describe the primary operation or interaction
- Names should be concise and descriptive
- Examples: `socratic-mirror`, `cybernetics-agent-seminar`

### 5. Multilingual Considerations

This repository may contain skills in multiple languages:

- **Skill name**: Use English (for command-line compatibility)
- **Description and content**: Can use any language
- **File encoding**: Ensure UTF-8 encoding
- **Test cases**: Can use any language for prompts

### 6. Git Workflow

After creating or modifying skills:

```bash
# Check status
git status

# Add new skill
git add skills/<skill-name>/

# Commit
git commit -m "feat: add <skill-name> skill"

# Push
git push origin main
```

### 7. Common Mistakes to Avoid

1. **Wrong directory path**
   - Don't assume skills should be in `~/.claude/skills/`
   - Always use this repository's `skills/` directory

2. **Workspace pollution**
   - Don't commit workspace files to git
   - Consider adding `*-workspace/` to `.gitignore`

3. **Permission issues**
   - This repository directory should be writable
   - No need to use `/tmp/` as temporary directory

## Repository Goals

- Help AI assistants deeply understand individual user preferences and habits
- Enable AI to continuously evolve through self-reflection and optimization
- Provide reusable skill modules to enhance AI-human collaboration efficiency

## Contact

For questions or suggestions, please contact the repository maintainer via GitHub Issues.
