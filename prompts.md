# Prompts

Store project prompts here.

## 2026-11-23

### Request 1
- **Asked:** Set up the project folders for a single-file web app, keeping `AGENTS.md`, `spec.md`, `prompts.md`, and `index.html` at the top level. Create `00_planning`, `01_data`, `02_validation`, and `03_output` with short README files, describe the layout in `AGENTS.md`, and add the file-placement rule.
- **Changed:** Created the top-level files and all four numbered folders with README files. Added layout and file-placement instructions to `AGENTS.md`.
- **Worked:** Yes. The layout was created and verified.

### Request 2
- **Asked:** After each request, add an entry to `prompts.md` recording what was asked, what changed, and whether it worked.
- **Changed:** Added this prompt-log entry format to `prompts.md` and recorded the folder setup and current logging request.
- **Worked:** Yes.

### Request 3
- **Asked:** Review `spec.md` in plan mode and identify missing considerations or improvements for a keyboard-operated tower crane game.
- **Changed:** Reviewed the specification and repository guidance, with no app or specification files modified. Prepared a requirements and implementation plan covering gameplay, crane physics, controls, scoring, validation, accessibility, and responsive behavior.
- **Worked:** Yes.

### Request 4
- **Asked:** Implement the prior recommendations for coordinate layout, capacity calculations, simple percentage tipping, simplified gameplay, controls, scoring, crane limits, responsive behavior, validation, and accessibility.
- **Changed:** Replaced `spec.md` with a concrete simplified specification covering the crane coordinate system, controls, percentage capacity, 90% warning and 100% tipping, fixed loads and 3-minute game loop, scoring, test cases, responsive layouts, touch controls, and basic accessibility.
- **Worked:** Yes.

### Request 5
- **Asked:** After every significant code change, summarize the change in a local commit message and do not push it.
- **Changed:** Added the Git workflow rule to `AGENTS.md`, including commit-after-significant-change and no-push instructions.
- **Worked:** Yes.

### Request 6
- **Asked:** Read `spec.md` and provide a short overview of the app plus a 3-to-5-stage build plan beginning with a page-layout mockup.
- **Changed:** Reviewed the specification and prompt log. No app code or specification content was changed; prepared an implementation plan for the mockup and subsequent gameplay stages.
- **Worked:** Yes.

### Request 7
- **Asked:** Execute Phase 1 by building the static page-layout mockup.
- **Changed:** Replaced the placeholder `index.html` with a responsive desktop/mobile mockup containing the crane worksite, staging area, building, side view, load chart, timer, score, capacity panel, delivery status, and control bar.
- **Worked:** Yes; layout was added without implementing gameplay.

### Request 8
- **Asked:** Execute Phase 2 by adding crane movement and live visual feedback.
- **Changed:** Added held-key and touch controls for trolley, hook height, and crane rotation; enforced radius and height limits; synchronized the map and side-view hook positions; added live radius, height, and capacity status; and added normal, 90% warning, and 100% tip feedback. Added a temporary F/Space demo-load toggle for testing capacity states.
- **Worked:** Yes; the app served locally and the implementation was committed.

### Request 9
- **Asked:** Explain in simple terms what went wrong while implementing Phase 2.
- **Changed:** Reviewed the Phase 2 work and prompt history. No app code was changed; prepared an explanation of patch-context, browser-validation, and verification difficulties.
- **Worked:** Yes.
