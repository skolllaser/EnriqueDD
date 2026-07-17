---
title: How to Create Custom Skills - Claude Help Center
date: 2026-06-12
tags: [Claude, Skills, Custom Skills, AI, Tutorial]
---

How to create custom skills
Skills are available for users on free, Pro, Max, Team, and Enterprise plans. This feature requires code execution to be enabled. Skills are also available in beta for Claude Code users and for all API users using the code execution tool.

Custom skills let you enhance Claude with specialized knowledge and workflows specific to your organization or personal work style. This article explains how to create, structure, and test your own skills.

## Best Skills Characteristics
- Solve a specific, repeatable task
- Have clear instructions that Claude can follow
- Include examples when helpful
- Define when they should be used
- Are focused on one workflow rather than trying to do everything

## Create a skill.md File
Every skill consists of a directory containing at minimum a skill.md file, which is the core of the skill. This file must start with a YAML frontmatter to hold name and description fields, which are required metadata. It can also contain additional metadata, instructions for Claude or reference files, executable scripts, or tools.

### Required Metadata Fields
- **name**: A human-friendly name for your skill (64 characters maximum)
  - Example: Brand Guidelines
- **description**: A clear description of what the skill does and when to use it. This is critical—Claude uses this to determine when to invoke your skill (200 characters maximum).
  - Example: Apply Acme Corp brand guidelines to presentations and documents, including official colors, fonts, and logo usage.

### Optional Metadata Fields
- **dependencies**: Software packages required by your skill.
  - Example: python>=3.8, pandas>=1.5.0

The metadata in the skill.md file serves as the first level of a progressive disclosure system, providing just enough information for Claude to know when the skill should be used without having to load all of the content.

### Markdown Body
The markdown body is the second level of detail after the metadata, so Claude will access this if needed after reading the metadata. Depending on your task, Claude can access the skill.md file and use the skill.

### Example skill.md Structure
```yaml
---
name: Brand Guidelines
description: Apply Acme Corp brand guidelines to all presentations and documents
---

## Overview
This skill provides Acme Corp's official brand guidelines for creating consistent, professional materials.

## Brand Colors
- Primary: #FF6B35 (Coral)
- Secondary: #004E89 (Navy Blue)
- Accent: #F7B801 (Gold)
- Neutral: #2E2E2E (Charcoal)

## Typography
- Headers: Montserrat Bold
- Body text: Open Sans Regular
- Size guidelines: H1: 32pt, H2: 24pt, Body: 11pt

## Logo Usage
Always use the full-color logo on light backgrounds. Use the white logo on dark backgrounds. Maintain minimum spacing of 0.5 inches around the logo.

## When to Apply
Apply these guidelines whenever creating:
- PowerPoint presentations
- Word documents for external sharing
- Marketing materials
- Reports for clients
```

## Adding Reference Files
Place supporting files in a `references/` folder within the skill directory. Reference them in your skill.md using relative paths.

## Adding Executable Scripts
Scripts go in a `scripts/` folder. Reference them in your skill.md.

## Testing Your Skill
1. Save your skill directory
2. Start a new conversation with Claude
3. Ask Claude to use your skill
4. Verify it works as expected

## Publishing Skills
Skills can be shared by copying the skill directory. For teams, consider using a shared repository or package manager.

[Original article](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)