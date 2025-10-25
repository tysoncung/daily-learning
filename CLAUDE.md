# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a personal daily learning and open source contribution tracking system. The primary goal is to maintain a daily contribution streak while documenting learnings, skills developed, and open source activities.

## Repository Architecture

### Core Structure
- **notes/**: Daily learning entries in markdown format (`YYYY-MM-DD.md`)
- **PROGRESS.md**: Live dashboard tracking streak, stats, achievements, and goals
- **README.md**: Repository overview and workflow documentation
- **Submodules**: Contains working copies of various awesome-list projects being contributed to

### Daily Note Format
Each note follows a consistent template with sections:
- What I Learned Today
- Code Snippets
- Open Source Contributions / Key Projects Worked On
- Technical Skills Practiced
- Resources
- Tomorrow's Goals / Goals for [Month]
- Reflections (optional)

Reference `notes/2025-09-12-example.md` for the canonical structure.

## Critical Policies

### NO AI Tool Mentions
**NEVER** mention "Claude", "Claude Code", or any AI assistant in:
- Commit messages (enforced by `.git/hooks/commit-msg`)
- Daily learning notes
- Documentation updates
- Co-Authored-By lines
- GitHub issue comments
- Pull request comments
- Code review comments
- Any public GitHub interaction

The git hook will block commits containing these references. If blocked, rewrite the commit message to be generic (e.g., "AI-assisted development" instead of "Claude Code").

### Writing Style for Public Comments (GitHub Issues/PRs)
**CRITICAL**: Comments must appear human-written to avoid detection as AI-generated.

**Rules**:
- Keep comments SHORT (1-3 sentences max)
- NO emojis or icons (❌ 🚀 ✅ 📚 etc.)
- Use casual language with occasional typos if natural
- Avoid overly structured formatting (no bullet points unless necessary)
- NO comprehensive lists or step-by-step guides
- Write like you're quickly typing a response, not composing documentation
- Use "I" statements: "I noticed...", "I think...", "I can fix..."
- Skip pleasantries and filler words

**Bad (AI-obvious)**:
```
Hello! 👋 I found several issues with this PR:

1. ✅ The code works well
2. ⚠️ Missing error handling
3. 📝 Documentation needs updating

Looking forward to your response! 🚀
```

**Good (Human-like)**:
```
Missing error handling on line 23. Also the docs should mention the timeout parameter.
```

OR

```
I can take a look at this. Probably just need to update the validation logic.
```

### Commit Message Style
- Use emoji prefixes sparingly: 📚 for learning updates, 🚀 for features, 🔧 for fixes
- Keep messages concise and descriptive
- Never include bot attributions or AI tool credits
- Example: `Learning updates: Days 13-14 (Sept 25, 30)`

## Common Workflows

### Creating Daily Learning Entry
```bash
# Automated via helper script (creates template)
~/daily-commit.sh

# Manual creation - use YYYY-MM-DD.md format
cd notes/
# Copy from notes/2025-09-12-example.md as template
```

### Updating Progress Dashboard
When updating `PROGRESS.md`:
1. Update streak count and date range
2. Increment contribution stats (PRs, issues, contributions)
3. Update monthly calendar view with [X] markers
4. Mark achievements as complete with ✅
5. Update goals progress (X/30 format)
6. Add new featured contributions if significant

### Syncing with Remote
```bash
# Repository uses 'master' branch (not 'main')
git push origin master
```

### Checking Daily Contribution Status
```bash
# Automated check (sends macOS notification if missing)
~/check-daily-contribution.sh
```

## Statistics Tracking

Track these metrics in PROGRESS.md:
- **Current Streak**: Days with format (Sept 11-15, 17-25, 30)
- **Total Contributions**: Overall GitHub activity count
- **PRs Opened/Merged**: Track both counts
- **Issues Resolved**: Bug fixes and validations
- **Documentation Improvements**: Docs/guides created
- **Days Active**: Unique contribution days
- **Projects Contributed To**: Different repositories

## Monthly Calendar Format
```
Mo Tu We Th Fr Sa Su
                   1
 2  3  4  5  6  7  8
 9 10 [11][12][13][14][15]
16 [17][18][19][20][21][22][23]
[24][25] 26 27 28 29
[30]

[X] = Contribution made
```

## Submodules

The repository contains several submodules for projects being actively contributed to:
- `awesome-devops-platform/`: Platform Engineering resources
- `awesome-fedify/`: ActivityPub framework resources
- `awesome-main/`, `awesome-nodejs/`, `awesome-typescript/`: Various curated lists
- `fedify/`: ActivityPub framework
- `tysoncung/`: GitHub profile repository

When updating these, commit changes within the submodule first, then update the parent repository reference.

## Goal Structure

Goals are organized hierarchically:
- **Week 1 Goals**: Initial setup and first contributions
- **Month 1 Goals**: 30-day milestones (streak, PR count, contribution types)
- **Long-term Achievements**: Major milestones with checkboxes

Mark completed goals with `[x]` and add ✅ emoji with completion details.

## Automation Scripts

External helper scripts (in `~/`):
- `daily-commit.sh`: Creates daily note template and commits
- `check-daily-contribution.sh`: Verifies daily contribution and sends alerts
- `daily-oss-helper.sh`: Finds good first issues
- `learning_tracker.py`: Python-based progress tracker with statistics

These scripts are referenced but live outside the repository.