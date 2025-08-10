# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Obsidian-based knowledge management vault focused on mathematics education and study notes, particularly Korean high school mathematics curriculum. The repository uses markdown files organized by subject topics with templates for consistent note-taking.

## Repository Structure

- **`고1수학-50일 수학/`**: High school first-year mathematics notes organized by topics
  - `01_수와 연산/`: Numbers and Operations
  - `02_문자와 식/`: Variables and Expressions  
  - `03_곱셈 공식과 인수분해/`: Multiplication Formulas and Factorization
  - `03_방정식/`: Equations
  - `05_부등식/`: Inequalities
  - `dashboards/`: Progress tracking and concept maps

- **`templates/`**: Note templates for consistent formatting
  - `topic-note.md`: Main concept note template with sections for definitions, formulas, visualization, examples, and connections
  - `example-problem.md`: Problem-solving template with difficulty ratings and solution steps
  - `daily-practice.md`: Daily practice tracking template
  - `test 템플릿.md`: Test preparation template

## Working with Templates

When creating new notes, use the existing templates as base structures. Key template fields include:
- `THEME`: Subject theme identifier
- `테마번호`: Theme number  
- `status`: Progress indicator (⚪ not yet, etc.)
- `difficulty`: Problem difficulty rating (★ to ★★★★★)

## Notes

- This is an Obsidian vault, so maintain compatibility with Obsidian's linking syntax using `[[double brackets]]`
- Templates use Templater plugin syntax (e.g., `<% tp.prompt() %>`)
- The vault is in Korean, focusing on Korean mathematics curriculum
- Preserve the existing folder structure and naming conventions when adding new content