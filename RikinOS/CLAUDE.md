# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an Obsidian vault for personal notes and learning materials.

## Structure

- **TODO.txt.md** - Daily thought dump and notes (dated entries with format `2025-12-3`)
- **Idea Stash.md** - Collection of ideas organized by date
- **Top-level .md files** - Courses and learning materials (Joy of React, Learning Rive, etc.)
- **assets/** - Images and media
- **templates/** - Obsidian templates

## Working with This Vault

- Notes use standard markdown with Obsidian-specific features (wikilinks `[[Note Name]]`, canvas files)
- TODO.txt.md is a running log - new entries go at the bottom with a date header
- After making any entry or changes to notes, commit and push to GitHub

## Idea Stash Workflow

When the user says something like "I have an idea" or "add this to my idea stash":

1. **Capture the idea** in `Idea Stash.md` with:
   - Date header (format: `## 2025-12-3`) - create new header if first idea of the day
   - Concise summary of the idea (1-3 sentences)
   - Relevant tags (e.g., `#idea/product`, `#idea/project`, `#idea/content`, `#idea/learning`, `#idea/life`)
   - Optional: brief notes on potential, next steps, or related ideas

2. **Format example**:
   ```
   ## 2025-12-3

   ### App that tracks daily water intake
   An app that gamifies hydration by letting you grow a virtual plant based on how much water you drink. Could integrate with health apps.

   `#idea/product` `#idea/app`
   ```

3. **When adding daily entries to TODO.txt.md**: Check if any ideas were added to the Idea Stash today and mention them as a reminder (e.g., "You also captured 2 ideas today in your Idea Stash").
