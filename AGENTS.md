# Agent Instructions

This project is a single-file web app. GitHub Pages serves `index.html` from the top level.

## Project layout

- `index.html` - the complete web app and must remain at the top level.
- `spec.md` - project requirements and specification.
- `prompts.md` - prompts used for planning or generating the app.
- `AGENTS.md` - repository instructions for agents.
- `00_planning/` - notes, sketches, planning documents, and drafts.
- `01_data/` - data files used by the app or project.
- `02_validation/` - hand calculations, test cases, and validation records.
- `03_output/` - screenshots, exported results, and other generated output.

## File-placement rule

Save every new file in the folder that owns its purpose:

- Use `00_planning/` for planning and design artifacts.
- Use `01_data/` for data.
- Use `02_validation/` for calculations and tests.
- Use `03_output/` for screenshots and exported results.
- Keep only the app entry point and project-level instruction/specification files at the top level.

## Git workflow

- After each significant code change, create a short commit message that summarizes the change.
- Commit the significant code change locally before starting unrelated work.
- Do not push commits. The user will push at the end.
